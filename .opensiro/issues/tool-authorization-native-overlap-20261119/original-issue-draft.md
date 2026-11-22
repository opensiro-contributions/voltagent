# Proposal: scoped delegate_task hold or subset after a child denial — Opensiro VSM architecture review

## Proposal in the project's own terms

### Is your feature request related to a problem? Please describe.

**What exists today:** VoltAgent's [`createDelegateTool`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts#L776-L857) resolves requested `targetAgents` and passes the complete valid list into `handoffToMultiple`, which starts handoffs in parallel. The existing [`onToolStart`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/hooks/index.ts#L190-L223) hook has a `void` return contract, rather than a typed decision that can restrict a selected subset before the handoff. The application can instead avoid delegation, wrap the tool or enforce permission at each child.

**What may be missing:** A developer composing a supervisor with a read-only Researcher and a separately authorized Writer might want to react to a *previous* denied child MCP write by holding the next `delegate_task` or dispatching only an authorized subset of the model-selected children, while preserving their existing identities and the application's permission limits. This is a hypothetical, testable scenario, **not** a reported security incident or a claim that VoltAgent currently bypasses tool permissions.

**Closest existing project-native solution:** Use the supervisor's existing hooks/tool wrappers for a whole-call veto and each child's MCP `can` authorization. This may already be sufficient for most users. A new callback is worthwhile only if a native-only wrapper cannot support a typed, observable **subset-of-already-selected-agents** decision without duplicating the internal delegation lifecycle.

**Existing discussion:** [#1177](https://github.com/VoltAgent/voltagent/issues/1177) (open since 2026-03-28; last updated 2026-09-06) requests per-tool authorization and mentions delegation scope narrowing. I reviewed its proposal and subsequent discussion; it does **not** establish a shipped supervisor decision port. [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390) is still open/unmerged and proposes an agent-level `toolGuard`; it does not modify `subagent/index.ts`. This proposal is about the *next team delegation*, **not** granting, denying or weakening access to a tool. If maintainers prefer to treat this as an extension of #1177 rather than a standalone issue, that is the right place to consolidate it.

### Describe the thing to improve

A narrow, **opt-in pre-dispatch delegation decision** at the existing `createDelegateTool` seam, after resolving registered children but before `handoffToMultiple`. An application-composed decision actor could return `allow`, `hold`, `selected subset` (only from the already-resolved child names), or `escalate` to the parent. The supervisor would consume correlated earlier child-denial feedback and the next `onHandoffComplete` result; the library must enforce the decision before child execution. No new permission can be minted, and disabling this option retains current behavior.

## How we reached this proposal — Opensiro VSM assessment

**Historical assessment:** [Accepted Opensiro Index assessment](https://github.com/opensiro/vsm-harness-index/blob/8f436270813b844aafc16917d69bc09661ef1544/assessments/vo/voltagent.md), Index commit `8f436270813b844aafc16917d69bc09661ef1544`, assessment blob SHA `c7dec10ee48c461833c33e0ceb408cd49ed57fdd`, review ref `44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de`, reviewed `2026-09-19`; Profile `0.2.3`, Skills methodology `0.3.5`. This is a frozen historical assessment, **not** a fresh grade or a product quality score.

**Boundary:** First-party `@voltagent/core` Agent, optional SubAgentManager team, tool/hook/MCP and workflow paths. External policy engines, MCP servers, VoltOps and human maintainer organization are outside the assessed runtime.

**Current original HEAD:** [VoltAgent/voltagent main@e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c](https://github.com/VoltAgent/voltagent/commit/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c), rechecked 2026-11-22. Current first-party delegation/hook source and original Issue/PR status were inspected separately from the frozen Index record.

| Function / plain-language role | Native role | Historical state | Current source-backed boundary |
| --- | --- | --- | --- |
| **S1 · Operations** | Agent/tool execution | A | Agent closes its own operational tool cycle |
| **S2 · Coordination** | Compose specialists | C | SubAgentManager and workflows expose optional team composition |
| **S3 · Current management** | Regulate active joint commitments | — | Existing hooks and tool policies do not establish a separate, model-owned team-level hold/subset decision with subsequent feedback |
| **S3* · Independent audit** | Independent corrective check | — | Hooks/logging alone do not prove a distinct independent reviewing actor |
| **S4 · Future adaptation** | External/future sensing | — | Current invocation routing is not evidence of prospective environmental response |
| **S5 · Identity/policy** | Ultimate policy | — | Application/parent retains permissions and ultimate authority |

State legend (historical *agent ownership*, not a maturity ranking): `A` = autonomous first-party decision/feedback closure; `C` = first-party developer-composable function-specific constructor; `P` = separately supported parent-governed S3–S5 closure; `A(P)` / `C(P)` = separately evidenced accompanying parent modes; `—` = no sufficient function path established at the reviewed boundary; `?` = evidence unresolved. These states do not require a project to implement every VSM function.

## Why this particular construction?

**Whole-repository prioritization:** The accepted historical vector already records S1=A and S2=C. The bounded follow-up tests whether a genuine S3 *current team dispatch* decision can be composed without changing ultimate application policy. S3* independent audit, S4 future adaptation and S5 policy are not targets here.

**Construction hypothesis:** Historical `S3=— -> S3=C` *only if* the composed supervisor can choose and enforce among lawful team-level alternatives and use a later handoff outcome to make its next decision. This is proposal-stage `GO / NEEDS_EVIDENCE`, not a shipped feature or regraded Index assessment.

**Native building blocks:** `delegate_task` and `handoffToMultiple`, existing `onToolStart` / `onToolError` / `onHandoffComplete` hooks, and MCP `can` checks. [Issue #1177](https://github.com/VoltAgent/voltagent/issues/1177) and [open PR #1390](https://github.com/VoltAgent/voltagent/pull/1390) own any per-tool authorization design decisions.

**Minimal proposed addition:** Prefer first testing a native wrapper/hook-only solution. If it cannot faithfully return a typed subset/hold effect before parallel handoffs, add one optional decision interface at that existing first-party boundary, **not** a new global governance subsystem.

**Scope exclusions:** Never expand permissions, add agents beyond the model-selected/registered targets, change a child's own MCP rights, launch a second scheduler or impose supervisor hooks on existing users.

## Proposed approach and validation

1. Reproduce the baseline with a Researcher and Writer, fixed application-level access, a real child MCP denial and one subsequent `delegate_task`.
2. Compare a pure existing hook/tool-wrapper solution with an optional typed `allow/hold/subset/escalate` decision before `handoffToMultiple`; capture which children actually started and correlate handoff outcomes to the subsequent choice.
3. Test missing/stale denial evidence, unregistered names, unauthorized added targets, concurrent delegations, callbacks throwing/timeouts and the disabled-option baseline. No child should receive permissions it lacked initially.

**Hypothesized benefit:** A consistent developer-facing way to replan only the *next* delegated team action based on prior operational evidence, without implementing a second delegation engine. User adoption, safety improvement and efficiency gains are **NOT_MEASURED**.

**How to falsify:** Demonstrate that the shipped `onToolStart` / wrapper, MCP `can` and `onHandoffComplete` already provide the same safe hold/subset/effect/feedback loop without a new first-party port; or show that child-denial feedback cannot be safely correlated before the next dispatch. Either outcome is a reason **not** to add an API.

**Cost status:** NOT_MEASURED. Native test execution: NOT_RUN. This issue suggests a bounded comparison, not an already validated implementation.

## Feedback requested

Would a type-safe, optional **pre-handoff target-subset decision** be useful, or is there a documented existing way to implement it using `onToolStart` and a composed wrapper? In particular, can a wrapped `delegate_task` preserve the current tracing, validation, parallel handoff and result lifecycle without copying SubAgentManager logic?

## Three independent ways to participate

- **VoltAgent-native:** Use the existing hook/MCP pattern or advise on the smallest first-party interface; maintainer product priorities control any implementation.
- **OpenSiro methodology:** Challenge the historical S3 classification independently in [Profile](https://github.com/opensiro/vsm-harness-profile) / [Skills](https://github.com/opensiro/vsm-harness-skills), without treating this proposal as a new grade.
- **Optional external experiment:** A developer can compare native-only vs proposed behavior in a lawful local project before asking for SDK changes.

## Research attribution and AI disclosure

[OpenSiro Upstream](https://github.com/opensiro/upstream) — [source-pinned capability case](https://github.com/opensiro-contributions/voltagent/blob/38642cd53f4c547ad4643fa110bd27b5c321c280/.opensiro/issues/tool-authorization-native-overlap-20261119/roadmap.md).

**AI involvement:** An AI assistant performed source review and drafted this research-driven feature proposal. No native implementation, executed test, measured benefit, current Index regrade or maintainer endorsement is claimed.

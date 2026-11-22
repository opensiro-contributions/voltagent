# VoltAgent — source-native S3 pre-dispatch construction technical contract

**Canonical storage:** `opensiro-contributions/voltagent@opensiro/meta:.opensiro/issues/tool-authorization-native-overlap-20261119/constructor-sufficiency.md`.
**Level 1 / Human decision Issue:** [issue.md](issue.md).
**Canonical decision receipt:** [roadmap.md](roadmap.md) — only source of accepted Index grades, six-function dispositions, P0/P1/P2 and verdict.
**Stage:** PLAN_ONLY / HYPOTHESIS → PROPOSAL-STAGE; code, tests and C classification not delivered. **DRAFT — NOT PUBLISHED**.

## 1. Function-specific construction boundary and methodology checks

**Source and mode boundary:** [VoltAgent main@e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c](https://github.com/VoltAgent/voltagent/commit/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c), @voltagent/core Agent with SubAgentManager team, first-party TypeScript delegation, hooks and MCP. Parent app, third-party MCP servers, policy issuer, VoltOps and maintainer governance excluded; original current and accepted Index historical record distinct.

**Target transition:** S3=— -> S3=C

**Six-function dependencies (S1/S2/S3/S3*/S4/S5):** S1 executing children must return actual results; S2 optional team delegation is already C; selected S3 supervises the *current next joint dispatch*; S3* independent review is not claimed from a tool hook; S4 prospective planning is not in scope; S5 permission grants remain with parent/application.

**Function witness:** An earlier read-only child's denied MCP action may prompt a supervisor decision before its next multi-child delegation. The supervisor may choose allow, hold, restrict to already selected/registered children or escalate, and observe later `onHandoffComplete` evidence before another choice.

**Counterfactual owner test:** Without the developer-composed deciding actor, SubAgentManager transports the caller-selected team and each child enforces its existing rights. Neither static hook transport nor a tool denial decides *which permitted subset should execute next* based on the earlier denial; this counterfactual requires verification against a composed native wrapper.

**Possible methodological negative control:** Parent-defined access and current first-party hooks could already close the identical team choice/return if application code wraps `delegate_task`; demonstrate this before adding a new core port. No inference about human or repository policy.

**Contributor / maintainer priorities:** Open [original #1177](https://github.com/VoltAgent/voltagent/issues/1177) and [unmerged PR #1390](https://github.com/VoltAgent/voltagent/pull/1390) show authorization interest, not adoption of this proposed S3 callback. Actual customer demand and maintainers' preference are NOT_STATED.

## 2. Source-pinned baseline and parallel native Track A / on-top Track B

**Original native workflow:** Supervisor tool `createDelegateTool` resolves `targetAgents` registered names then invokes `handoffToMultiple` in parallel. Tool `onToolStart` currently returns void; child MCP `can` and error/completion hooks provide separate permission and feedback paths.

**Closest existing solution:** Wrap the parent `delegate_task` or reject its entire call via `onToolStart`; handle authorization at every child. No new permission system is necessary for basic deny/allow.

**Relevant original Issues/PRs:** [#1177](https://github.com/VoltAgent/voltagent/issues/1177) is OPEN since 2026-03-28, last updated 2026-09-06, with per-tool policy discussion. [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390) is OPEN/unmerged at `0fb458490703f5a89f6bb0e196c0c4f79bf95cb1` as observed 2026-11-22; it modifies Agent/hooks/types/tests, not the native SubAgentManager dispatch. Neither has been validated as a shipped S3 team chooser. Historical merged #870 is separate; no automatic Index regrade.

| Required C link | Track A: current first party | Track B: smallest proposed addition | Falsifier |
| --- | --- | --- | --- |
| Team discretionary choice | Model-selected registered targets; onToolStart observing/veto | Optional typed hold/subset/escalate after target resolution | A supported wrapper already selects the same subset safely |
| Effect + return | `handoffToMultiple`, onToolError, onHandoffComplete | Enforce approved subset before any child starts and correlate later result | Original first-party API lacks correlation or parent rights |
| Parent boundary | MCP can and application grants | Deny added/unregistered child and fail closed on stale facts | Proposed gate bypasses/creates grants |

**On-top distinctness:** Only a typed pre-parallel handoff effect and later team-level feedback would be new. An application-supplied toolGuard is a different per-tool authorization problem; no independent user demand is inferred from that PR.

**Source ambiguity / rights blockers:** Native-only wrapper completeness and denied-child correlation are not experimentally verified. A source-first test may eliminate this proposal. External publication also requires exact owner consent; no such consent is inferred from this case.

## 3. Minimal complete S3 first-party C construction

**Required property:** Expose a first-party developer-composable autonomous supervisor decision/effect/feedback path for one current team dispatch, within immutable parent-issued rights.

| Native component | Shipped source | Proposed bounded edit | Owner/effect/return |
| --- | --- | --- | --- |
| SubAgentManager.createDelegateTool | [subagent/index.ts](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts#L776-L857) resolves names | Optional decision callback before handoffToMultiple; only hold or already-selected subset | App-composed supervisor chooses; SDK enforces before child work |
| Hooks/tool lifecycle | [hooks/index.ts](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/hooks/index.ts) void onToolStart and completion/error | Correlate previous denial to next lawful choice and return result | Supervisor observes effect, adjusts subsequent choice; parent retains grants |

**Architectural C-sufficiency argument:** Compare first (1) application-owned existing wrapper/hooks, (2) typed callback confined to SubAgentManager and (3) a broader toolGuard policy that belongs to Issue #1177. (1) is cheapest and should win when equivalent; (2) is a coherent optional S3 constructor only if it adds necessary typed subset enforcement and feedback without bypass; (3) is not a substitute for the team's current discretionary choice. The proposed single native hook is not sufficient alone unless an actual composed actor chooses and later sees the return.

**Explicit non-goals:** No new permission grants, general S5 policy, persistent scheduler, arbitrary cross-project actor, unbounded retry/relaunch, S3* audit or external S4 feed.

**Implementation dependency graph:** P1 verify actual native-only comparator, legitimate child-denial evidence, selected-name restriction and callable callback safely; then P0 expose minimal optional team decision and real return; after that execute first-party tests, preserve disabled defaults and re-evaluate C with Index owner separately.

## 4. Priorities, optional alternative and stopping rules

**P0 and P1:** P0 is one optional S3 team-delegation choice/effect/feedback chain; P1 covers denial correlation, parent allowlist, no-added-target guard, parallel safety, timeout/failure behavior and native test coverage. These are exactly the canonical case priorities, not separate product work.

**P2:** NONE; no second function or universal control plane.

**Alternative path:** A developer wrapper which guards the full `delegate_task` and reinvokes only approved children with unchanged SDK metadata is preferable if fully supported by current APIs. Preserve MCP can and toolGuard ownership.

**Stop:** Stop if a shipped supported wrapper already supplies the same effect/feedback; parent rights cannot be preserved; any child can start before the decision; evidence attribution is unreliable; or original maintainers do not approve external design discussion. Not measured demand is not itself an architecture falsifier.

## 5. Future source-native acceptance — derive tests, do not copy a matrix

**Native test commands and entry points:** Proposed tests in `packages/core/src/agent/agent.spec.ts` and new/extended SubAgentManager tests; run with original repository's `pnpm`/Vitest commands after confirming current package scripts. **NOT_RUN** in this plan-only pilot; do not claim a passing native suite.

**Positive functional closure:** Given two already registered/parent-approved child agents, an actual earlier denied MCP write and a subsequent `delegate_task`, the composed supervisor selects one permitted target; the SDK dispatches exactly that target and delivers real handoff outcome to next choice.

**Independent alternative (where applicable):** Same parent and children with no previous denial choose ALLOW both; a stale denial causes HOLD/ESCALATE, which distinguishes discretionary current allocation from a hardcoded veto.

**Negative authority and compatibility (where applicable):** Disallow unregistered/additional targets, revoked parent rights, stale previous denial, missing prior feedback, concurrent changing dispatch, callback timeout and side-effect before verdict; no opt-in returns identical original tool behavior.

**Matched native alternative:** Compare the exact two-child test against a pure onToolStart/tool-wrapper solution with identical rights and input. If it matches functionality, prefer no new core callback.

| Proposed native case | Source-supported setup | Expected effect | Stop |
| --- | --- | --- | --- |
| Optional subset on next call | Existing delegate_task and onHandoffComplete + hypothetical callback | Only selected registered child starts, later completion informs next choice | Any extra child executes |
| Disabled baseline | Current shipped createDelegateTool without new callback | Unchanged parallel handoff behavior, existing child permissions | Regression or new denial |
| Adversarial invalid target | Requested child not already registered/selected | No unauthorized child or privilege escalation | Bypass or fail-open |

## 6. Proposal verdict, falsification, evidence ownership and handoff

**Proposal-stage decision:** GO

**Research disposition:** NEEDS_EVIDENCE

**Primary falsifier:** The current first-party tool wrapper and callbacks already realize safe, typed-enough subset/hold and next-operation return; no new port is necessary. **Validation state:** NOT_RUN.

**Ownership of truth:** Profile owns VSM semantics; Skills methodology; Index accepted grades/reassessment; original VoltAgent code, Issues, tests and maintainer decisions; [roadmap.md](roadmap.md) owns this case's research verdict.

**Cost status:** NOT_MEASURED.

**Next permitted action:** Test native-only comparator, verify original source and PR overlap, prepare exact native-publication payload for separate owner consent; do not publish or implement from PLAN_ONLY.

**Human backlink:** [issue.md](issue.md); **case receipt:** [roadmap.md](roadmap.md).

**AI disclosure:** AI assistance drafted this technical contract. No native test PASS, independent human approval, current Index grade, external publication or authority transfer is claimed.

# VoltAgent — team-level execution-rights current control (Wave 4)

**Level 1 / Human. PLAN_ONLY; independent source-first Wave 4 comparison.** Source-first [checkpoint](https://github.com/opensiro/upstream/issues/58#issuecomment-7043540206) precedes historical-case inspection; the old NO_GO remains in Git history.

**Target transition:** S3=— -> S3=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

[roadmap.md](roadmap.md) (canonical) · [constructor-sufficiency.md](constructor-sufficiency.md) (technical) · [original Issue #1177](https://github.com/VoltAgent/voltagent/issues/1177) · [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390)

**Proposal in plain language:** give an opt-in VoltAgent team a first-party control point that can *temporarily narrow, hold or reassign* tool-capable work after observing live authorization results, then see the outcome of the next action. The application owner fixes a non-escalating upper grant ceiling; this is not a new policy maker. The benefit remains **hypothetical**, not measured or requested by maintainers.

**Historical Index (accepted, not current regrade):** [VoltAgent](https://github.com/opensiro/vsm-harness-index/blob/8f436270813b844aafc16917d69bc09661ef1544/assessments/vo/voltagent.md), blob `c7dec10ee48c461833c33e0ceb408cd49ed57fdd`; review ref `44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de`, reviewed `2026-09-19`, Profile `0.2.3` / Skills methodology `0.3.5`. Historical vector: **S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—**. Source version separately pinned to [main@e9fc599f](https://github.com/VoltAgent/voltagent/commit/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c).

## Six-function source census

| Function | Accepted state | Current observed owner / limitation | Wave 4 priority |
| --- | --- | --- | --- |
| **S1 · Operations** | A | Agent model/tool execution with results | Existing; no extra C |
| **S2 · Coordination** | C | Optional SubAgentManager delegates work and synthesizes handoff results | Existing; no new coordinator |
| **S3 · Inside-now management** | — | Shipped authorizers are per-call; a whole-team restrictive decision and return is not demonstrated | **P0 proposed C, hypothetical** |
| **S3* · Independent audit** | — | Hook/trace logging alone does not own independent corrective audit | No target |
| **S4 · Outside/future** | — | Model/tool options do not demonstrate prospective change adaptation in this scenario | No target |
| **S5 · Policy/identity** | — | App/user retains role policy and ultimate access grants | Parent-reserved |

Historical state is not a quality score; deliberate S3 omission is UNVERIFIED. This is one installed multi-subagent runtime, not VoltOps or maintainer governance.

## Native reuse versus new function

- **Shipped:** MCP [`authorization.can`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/mcp/authorization.md), [agent tool hooks](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/hooks/index.ts), [delegation](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts), [suspend/resume](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/workflows/suspend-resume.md); native per-agent wrappers are cheaper for static access.
- **Original proposed:** [Issue #1177](https://github.com/VoltAgent/voltagent/issues/1177) and still **OPEN/UNMERGED [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390)** aim at agent-local tool guards. [PR #821](https://github.com/VoltAgent/voltagent/pull/821) is separate concurrency work.
- **Our P0 (PLAN_ONLY):** versioned team access/denial/dispatch snapshot -> separately composed current S3 choice `keep/narrow/hold/reassign/escalate` -> enforce through local/provider/MCP/delegation without exceeding parent rights -> correlate next result to the decision.
- **Important non-overlap:** existing separate [supervisor-commitment S3 case](https://github.com/opensiro-contributions/voltagent/blob/78496f45b5475a42b409eac4b4aa3a396b907836/.opensiro/issues/supervisor-commitment-control-20261119/roadmap.md) deals with commitments/budgets, not grants; new case must not implement a duplicate queue or double-count the same S3 controller.

**Falsifier:** show that shipped app policies, MCP `can`, hooks and supervisor already construct the complete same team-level actor/feedback loop safely, or that no non-escalating enforcement can cover all tool paths. That changes this scoped GO to NO_GO without requiring maintainer approval as an analytical veto.

**P1:** tests for allowed/denied tools, live narrowing, child non-escalation, stale grants, missing actor, retries and next-result correlation. **P2:** none. **Native tests:** NOT_RUN. **Costs:** NOT_MEASURED. **Fork metadata:** ACTIVE/ALLOW for internal case only. **External publication:** none. Original maintainers own product decisions.

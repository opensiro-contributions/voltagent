# VoltAgent — composable S3 current-commitment control (OpenSiro roadmap)

**PLAN_ONLY · proposed GO · NEEDS_EVIDENCE · DRAFT — NOT PUBLISHED**

**One-sentence proposal:** Reuse VoltAgent's shipped supervisor/delegation and usage hooks to propose a bounded, developer-composable current resource/commitment manager for multi-subagent teams; no permission expansion or duplicate tool guard.

**Canonical receipt:** [roadmap.md](roadmap.md). **Technical companion:** [constructor-sufficiency.md](constructor-sufficiency.md).
**Working fork:** opensiro-contributions/voltagent · case: .opensiro/issues/supervisor-commitment-control-20261119/.
**Target transition:** S3=— -> S3=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

## 1. Why Opensiro and accepted six-function starting point

OpenSiro tests whether reusable organizational descriptions and developer-composed decision contracts, informed by VSM, reduce agent-harness design/integration cost. Savings are not established and the maintainer is under no obligation to adopt VSM.

**ACCEPTED HISTORICAL INDEX:** **S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—**, [assessment](https://github.com/opensiro/vsm-harness-index/blob/b6318e9fb855c20a0a48dfd0ea03f78aaafbb320/assessments/vo/voltagent.md) at Index b6318e9fb855c20a0a48dfd0ea03f78aaafbb320; blob c7dec10ee48c461833c33e0ceb408cd49ed57fdd; review ref 44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de on 2026-09-19; Profile 0.2.3 / Methodology 0.3.5. These labels are ownership modes, not quality ratings or new-HEAD grades. A = autonomous owner; C = developer-composable function owner; P = legitimate parent-controlled S3/S4/S5; — = no bounded evidenced path; ? = unresolved.

Current original [HEAD e9fc599f](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/README.md) was independently screened across code, API, configuration, docs, PlanAgent, optional supervisor, memory, workflows, guardrails, hooks, tests/CI, contributor policy and original Issues/PRs. The boundary is a configured open-source team of specialist Agent units; external model infrastructure, separate VoltOps and maintainer governance are not credited. Original review is 61 days old, a source-drift caution only.

| Function / plain-language role | Historical Index state | Current owner / closure and disposition |
| --- | --- | --- |
| **S1 · Operations** | A | Running Agent chooses model/tool actions and uses returned results. No constructor priority. |
| **S2 · Coordination** | C | Shipped SubAgentManager supervises specialists and returns results; keep this first-party coordination path. |
| **S3 · Current management** | — | Per-task routing/maxSteps is not verified whole-team shared resource allocation. P0: propose composed manager with enforceable team commitments and feedback. |
| **S3* · Independent review** | — | Evals/guardrails/hooks observe or block locally; independent organizational audit right is not shown. DEFER; no invented reviewer. |
| **S4 · Future adaptation** | — | Dynamic config/fallback not a demonstrated prospective owner with future disturbance-response cycle. NO_TARGET for this scenario. |
| **S5 · Identity/policy** | — | Application developer/human owns policy, permissions and budgets. Respect parent authority; NO_TARGET. |

The absence of current S3 evidence is not a finding that VoltAgent is defective. No intentional omission is inferred without source evidence. Maintainer interest in this specific S3 design: NOT_STATED; prior authorization Issue #1177 is a different user need.

## 2. Operator outcome and proposed construction

**Target transition:** S3=— -> S3=C (hypothesis, not changed Index grade).
**Scenario:** HYPOTHETICAL application with two independently working specialists, overlapping high-priority commitments and a finite shared model/tool budget. The operator preapproves allowed options and budget bounds. Under changing current commitments, a developer-composed autonomous manager chooses admit, defer, hold or reassign before new specialist work starts.

**Best native alternative:** manual task sequencing and application queue, per-Agent maxSteps, customized supervisorConfig and existing hooks; OPEN [traffic PR #821](https://github.com/VoltAgent/voltagent/pull/821) might provide queue/priority/usage after an actual merge but is not shipped now.

**Expected benefit:** possible bounded current-team priority control under changing load; entirely HYPOTHETICAL, not measured. A plain traffic limiter may be enough. The distinctive requirement is the *organizational choice and returned outcome*, not a queue brand name.

## 3. Track A versus independent Track B

Track A: [SubAgentManager delegation](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts), [hooks](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/hooks.md), [subagent guide](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/subagents.md), [workflow suspend/resume](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/workflows/suspend-resume.md), [OPEN #821](https://github.com/VoltAgent/voltagent/pull/821) at ef8fd5c3397a1ca8c8dc785c9b999cbf66650e54. Adjacent OPEN [#1390 toolGuard](https://github.com/VoltAgent/voltagent/pull/1390), [#1219 validators](https://github.com/VoltAgent/voltagent/pull/1219), [#1475 handoff fix](https://github.com/VoltAgent/voltagent/pull/1475), [#1541 persistence](https://github.com/VoltAgent/voltagent/pull/1541) and [#1549 retry](https://github.com/VoltAgent/voltagent/pull/1549) must not be duplicated.

| Required S3 sufficiency | Shipped/parallel Track A | Smallest new Track B |
| --- | --- | --- |
| Live current commitments, lawful options and decisive autonomous choice | Delegation and usage hooks exist; #821 OPEN adds traffic counters/priority but not proven team decision ownership | Developer-configured S3 actor reads versioned team ledger and chooses admit/defer/reassign/hold under parent policy |
| First-party enforceable effect and return | Subagent dispatch and onHandoffComplete provide supported enforcement location and usage/results | Atomic pre-dispatch reserve/defer/commit plus cancellation release and task-linked completion/error/usage fed back to manager and supervisor |
| No autonomous manager installed | Native supervisor and human queue still available | Preserve unchanged baseline; never auto-install a new S3 owner |

## 4. Priority and minimum construction

**P0:** Bounded S3 decision interface with first-party versioned admission/reservation and linked outcome feedback over a team of subagents.
**P1:** Recheck #821's accepted state and diff before engineering; validate an actual cross-agent resource conflict and legitimate user policy; design atomic capacity/release and test against the simplest native sequential/traffic control.
**P2:** NONE.

**C sufficiency:** PROPOSED_C_SUFFICIENT at design/proposal stage only; the complete chain is plausible from the source's current extension seams plus a necessary first-party dispatch-and-return addition. It is not a shipped proof.

## 5. Proposed tests and falsifier

Positive: in a two-specialist test with limited shared capacity, composed manager observes live commitments, decides between two lawful resource allocations, native dispatch honors the selected choice, and later success/failure/usage reaches the manager and supervisor.

Negative: no manager preserves current native behavior; unauthorized option, revoked cap, stale ledger, cancellation and failed dispatch never commit or falsely report completion.

**Falsifier:** #821 or simplest native app queue gives equivalent lawful task-level allocation and feedback without the new C path, or new actor cannot enforce its decision without exceeding parent rights. Native tests NOT_RUN, benefit/cost NOT_MEASURED.

## 6. Options, publication and next decision

Do not implement or announce a new tool authorization guard, create an S5 policy owner, change Index grades or contact original maintainers now. Keep existing original PRs with their owners. Do a matched native witness first; only separately authorized native design/implementation if a distinct case survives. Profile/Skills corrections: NONE established. Independent MIT-permitted domain experiment: optional, not executed.

**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

This is a proposal-stage source-grounded GO to explore a specific S3=C architecture, not an implementation or external publication approval. Current fork owner state ACTIVE/ALLOW permits internal metadata only. Public fork GitHub Issues/PRs and any original maintainer communication each require separate current-conversation approval for the exact text/destination.

**AI disclosure:** Prepared with AI assistance. No native test, measured benefit, independent maintainer validation or accepted reassessment is claimed.

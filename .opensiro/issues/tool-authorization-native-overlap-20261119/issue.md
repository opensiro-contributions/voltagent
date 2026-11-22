# VoltAgent — opt-in pre-dispatch S3 team decision (Opensiro roadmap)

**PLAN_ONLY · proposal-stage GO · research NEEDS_EVIDENCE · DRAFT — NOT PUBLISHED**

**One-sentence proposal:** Let a developer compose an optional, bounded supervisor that can hold or restrict the already-selected `delegate_task` children after a prior child tool denial, then consume a real subsequent handoff result.

**Canonical decision receipt:** [roadmap.md](roadmap.md) — authoritative historical Index pins, S3 target, P0/P1/P2, decision and falsifiers.
**Technical companion:** [constructor-sufficiency.md](constructor-sufficiency.md) — precise first-party interface, native Track A/B and future tests.
**Working fork:** `opensiro-contributions/voltagent` · **Case:** `.opensiro/issues/tool-authorization-native-overlap-20261119/` on `opensiro/meta`.

## 1. Why Opensiro and central accepted VSM assessment

**Why Opensiro:** An organizational function should be identified by who chooses and closes a decisive feedback loop, not by the existence of a hook or controller name. This is a source-grounded but hypothetical engineering proposal; it is not proof of cost savings or a demand from VoltAgent users.

> **ACCEPTED HISTORICAL INDEX — not a current HEAD regrade**
>
> **S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—**
>
> [Accepted Index assessment](https://github.com/opensiro/vsm-harness-index/blob/8f436270813b844aafc16917d69bc09661ef1544/assessments/vo/voltagent.md), Index `8f436270813b844aafc16917d69bc09661ef1544`, blob `c7dec10ee48c461833c33e0ceb408cd49ed57fdd`, review ref `44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de`, reviewed 2026-09-19; Profile 0.2.3 / Skills 0.3.5.

**Repository-wide audit:** [VoltAgent/voltagent main@e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c](https://github.com/VoltAgent/voltagent/commit/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c), rechecked 2026-11-22. Boundary: first-party @voltagent/core Agent, optional SubAgentManager teams, MCP authorization, hooks and workflows. Current source paths for Agent/tool lifecycle, `subagent/index.ts`, authorization and hooks; original Issues #1177 and PR #1390 (open/unmerged) were checked. External MCP servers, VoltOps and the human maintainer organization are excluded.

| Function / plain-language role | Historical Index state | Current source-backed owner/closure | Candidate / exclusion |
| --- | --- | --- | --- |
| **S1 · Operations** — primary agent work | A | First-party Agent operates tools and returns results | NO_TARGET — autonomous operation exists |
| **S2 · Coordination** — compose specialists | C | Optional SubAgentManager/workflows coordinate subagents | NO_TARGET — composable path exists |
| **S3 · Current management** — team commitments | — | Static application-level checks and hook transports do not prove a team-level discretionary hold/subset/feedback owner | P0 S3=C hypothesis |
| **S3* · Independent review** — corrective audit | — | Traces and hook callbacks are not a separately independent reviewer | NO_TARGET |
| **S4 · Future adaptation** — outside change | — | Invocation routing does not prove prospective external sensing | NO_TARGET |
| **S5 · Identity/policy** — ultimate rights | — | Parent/application owns permission grants and policy | NO_TARGET |

**Interpretation:** `A` = first-party autonomous ownership of a closed decision; `C` = developer-composable first-party functional constructor; `P` = supported parent-governed S3–S5 control; `A(P)` and `C(P)` = evidenced additional parent modes; `—` = bounded lack of a material evidenced function; `?` = unresolved evidence. These are **ownership categories, not quality ranks**. Historical states are not today's ratings or a demand to build all six functions.

**Priority rationale:** Only S3 suggests a scoped new constructor with a specific native handoff seam, lawful alternatives, an operational effect and a later return. S1 already A; S2 already C; S3* and S4 are not justified as additional targets, and S5 remains with the parent.

**Deliberate exclusions / methodology challenge:** Human/application tool permissions and ultimate organizational authority are outside the agent runtime's S5 boundary; maintainer intent to construct an S3 callback is NOT_STATED. A current-source demonstration of equivalent hook composition would falsify our claimed missing C link.

**Contributor / maintainer interests (OPTIONAL):** Issue #1177 discusses per-tool authorization; PR #1390 implements a proposed toolGuard and remains OPEN_PR. Neither constitutes maintainer approval of this distinct S3 design.

## 2. Selected construction hypothesis and operator outcome

**Target transition:** S3=— -> S3=C

**Function-specific disturbance:** HYPOTHETICAL — after a read-only Researcher receives a legitimate MCP write denial, the supervisor considers a later `delegate_task` involving both Researcher and authorized Writer.

**Proposed C capability (P0):** An application-composed supervisory agent chooses `ALLOW / HOLD / SUBSET_OF_SELECTED / ESCALATE` within parent-authorized rights. A first-party gate applies the choice before any new parallel child handoffs; next handoff completion/denial is correlated back to the supervisor's following choice.

**Best native operator alternative:** Use the first-party [`onToolStart`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/hooks/index.ts) hook to veto a whole call or a composed wrapper, with separate child MCP `can` checks. Prefer this if it covers the same hold/subset/feedback behavior safely.

**Expected user benefit:** HYPOTHETICAL — replan the next team dispatch without duplicating the internal delegation implementation. No incident, actual customer demand or measured benefit is claimed.

**Architectural sufficiency argument:** Existing registered-child resolution, `onToolError` and `onHandoffComplete` provide transport/feedback. A missing typed pre-`handoffToMultiple` decision for an authorized subset could provide a complete developer-composable S3 choice/effect/return chain; the existence and necessity of this gap remain to be tested.

## 3. Existing native work versus missing construction

**Track A — native coverage:** SHIPPED: [createDelegateTool](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts#L776-L857), `onToolStart` with void return, hook errors/completions and MCP permission checks. ISSUE_ONLY: [#1177](https://github.com/VoltAgent/voltagent/issues/1177). OPEN_PR, unmerged: [#1390](https://github.com/VoltAgent/voltagent/pull/1390) toolGuard, not a change to subagent dispatch.

**Track B — independent on-top C construction:** Prefer a native-only wrapper experiment. Only if it cannot provide equivalent lawful selected-subset behavior, propose an optional typed gate after resolving target agents and before `handoffToMultiple`, with an observed previous denial and a later result.

| C sufficiency requirement | Current original (Track A) | Minimal possible addition (Track B) |
| --- | --- | --- |
| Supervisory choice over selected team | Hook can observe or reject a whole tool call | Optional ALLOW/HOLD/SUBSET_OF_SELECTED/ESCALATE result, only for known selected names |
| Enforceable next action and return | Parallel handoffs, hook errors, completion result | Enforced pre-dispatch effect and correlated feedback to next decision |

**Distinctness and falsifier:** If current `onToolStart` plus wrapper/MCP `can` and `onHandoffComplete` safely produces the same subset/hold/return loop without reproducing SubAgentManager logic, no new core callback should be proposed. Avoid duplicating #1177 or PR #1390.

## 4. Priorities and minimum sufficient result

- **P0:** A complete optional S3 current team-delegation decision and effect/feedback loop at the native `delegate_task` boundary, only if native-only composition is insufficient.
- **P1:** Prove attribution of child denial, typed named-subset restriction, parent rights, parallel race/timeout safety, real subsequent handoff return and first-party TypeScript tests.
- **P2:** NONE; no other VSM function or general policy layer.

**Proposed C-sufficiency verdict:** PROPOSED_C_SUFFICIENT as a falsifiable, bounded design. Not implemented, not tested, and not accepted into the Index as C.

## 5. Proposed acceptance and stop gates

**Future positive test:** Given a permitted Researcher/Writer pair and a previous child write denial, the composed supervisor chooses a lawful subset of the next registered targets, only those children start, and actual completion informs the next decision.

**Future negative test:** Parent restrictions, forbidden/unregistered targets, stale denial receipt, missing callback, concurrent delegation, timeout and lost result do not permit extra child execution; without the opt-in hook existing defaults remain unchanged.

**Proposed falsifier:** Existing hook/tool-wrapper composition already supports the identical safe subset decision and return, or the parent/child boundary cannot enforce the decision reliably.

**Validation state:** NOT_RUN; source-only PLAN_ONLY research. No test success or budget savings claimed.

## 6. Independent paths

**Original-native contribution:** Use and evaluate the existing hooks and #1177 / PR #1390 first. Any original Issue is a separate publication decision, not an implied GitHub post.

**Profile / Skills:** Methodology questions about agent-owned S3 versus static permission checks belong to the owning research repositories, not to VoltAgent's maintainer queue.

**Domain fork:** NONE proposed; a permitted local developer experiment could compare native-only and candidate behavior without upstream adoption.

## 7. Cost hypothesis

Engineering, testing and maintenance cost of a new gate must be compared against a native-only wrapper on the same next-delegation task. **Cost status: `NOT_MEASURED`**; no numerical benefit.

## 8. Decision / handoff

**Proposal-stage decision:** GO

**Research disposition:** NEEDS_EVIDENCE

**Decision reason / next permitted step:** Test a minimal native-only hold/subset wrapper first, validate exact child-denial correlation and inspect original PR #1390 again before any implementation or separately approved original-facing Issue. If native-only supports the complete loop, stop without new API. Do not infer a fixed-budget/authorization user demand.

**Agent/developer handoff:** [constructor-sufficiency.md](constructor-sufficiency.md), [roadmap.md](roadmap.md) and the exact current-original feature form.

**Rights and publication:** VoltAgent original MIT; verified working fork `opensiro-contributions/voltagent` owner `ACTIVE / ALLOW` for internal case work only. No external original/fork GitHub Issue, PR, comment or changed code is authorized by this draft; obtain current-conversation exact title/body approval and honor original contributor policy.

**AI disclosure:** Prepared with AI assistance. Independent native tests, external human review, maintainer acceptance and an S5 rights grant are NOT claimed.

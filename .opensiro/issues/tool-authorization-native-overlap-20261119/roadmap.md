# VoltAgent — Wave 4 assessment-neutral team action control (2026-11-20)

- Receipt contract: proposal-gate
- Original repository: VoltAgent/voltagent
- Original HEAD: e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c
- Observed at: 2026-11-20
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/8f436270813b844aafc16917d69bc09661ef1544/assessments/vo/voltagent.md
- Accepted assessment blob SHA: c7dec10ee48c461833c33e0ceb408cd49ed57fdd
- Accepted review ref: 44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de
- Accepted reviewed at: 2026-09-19
- Accepted Index commit: 8f436270813b844aafc16917d69bc09661ef1544
- Accepted Profile version: 0.2.3
- Accepted Skills methodology version: 0.3.5
- Accepted VSM vector: S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—
- System in focus: First-party VoltAgent @voltagent/core Agent and optional multi-subagent team, including local/provider tools, MCP authorization, delegation and workflow hooks; external MCP servers, external policy engines, VoltOps and maintainer governance excluded
- Repository-wide source map: https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/README.md; https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/agent.ts; https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/hooks/index.ts; https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts; https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/tool/manager/ToolManager.ts; https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/mcp/authorization/index.ts; https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/mcp/authorization.md; https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/workflows/suspend-resume.md; https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/guardrail.ts; https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/agent.spec.ts; https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/LICENCE; https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/CONTRIBUTING.md; original Issues/PRs #1177/#870/#1390/#821/#1549; accepted Index
- Evaluation object: Optional S3=C team decision about the *next* native `delegate_task` dispatch after a child's tool-authorization denial, bounded by existing application-set grants; not S5 policy issuance, toolGuard or budget scheduling
- Existing-work overlap: SHIPPED MCP authorization can, tool wrappers, hooks, supervisor delegation and workflow suspension; OPEN/UNMERGED original toolGuard PR #1390; distinct pre-existing OpenSiro supervisor-commitment S3 proposal (resource/commitment admission) is not shipped and must not be duplicated
- Our on-top contribution: PLAN_ONLY minimum first-party extension: an opt-in typed `SupervisorConfig` decision hook in `SubAgentManager.createDelegateTool` after `targetAgents` resolution and before parallel `handoffToMultiple`; a developer-composed current S3 actor chooses `ALLOW/HOLD/SUBSET_OF_SELECTED/ESCALATE` using parent-owned rights and linked child denial/return, never creates new grants or agents
- Incremental benefit: HYPOTHETICAL owner outcome: after a read-only subagent receives an MCP denial, constrain the supervisor's next model-selected `delegate_task` call before child work, receive later handoff result/usage, and adjust the next decision; not a reported incident, measured gain, product preference or shipped capability
- Decision scope: Post-v0.18.1 source-native refinement of the same Wave 4 architectural GO/NEEDS_EVIDENCE; a narrow current S3 choice at existing delegation boundary, not a broad cross-tool policy controller or Index regrade
- Target transition: S3=— -> S3=C
- Priority rationale: S1 is already autonomous and S2 already composable; S3 has a source-mapped team-wide current-state/choice/action/return candidate only if the control is genuinely cross-boundary and not just a policy callback; S3*/S4 lack this case's independent external evidence loop; S5 policy remains parent-owned
- P1 dependencies: Prove real child MCP denial reaches an attributable `onToolError`/parent handoff context, typed pre-parallel dispatch HOLD or selected-subset action under fixed rights, next `onHandoffComplete` feedback, stale/race/failure safety, and equivalence test against shipped `onToolStart` veto and MCP `can`; original PR #1390 remains unmerged
- P2 optional: NONE; no universal cross-tool authorization engine, no extra budget/task scheduler, no S4/S5 change
- Proposed C construction: Existing `createDelegateTool` resolves `targetAgents` by registered name before `handoffToMultiple`. Add an optional typed `SupervisorConfig` callback at exactly that seam; app-composed S3 actor uses a correlated previous child tool-denial report and parent-fixed rights to decide `allow`, `hold`, `subset of already selected registered children` or parent escalation. First-party dispatch enforces before running children; existing `onHandoffComplete` result/usage and tool errors return to subsequent S3 decisions. This port is HYPOTHETICAL, not shipped
- C sufficiency falsifier: Shipped supervisor `onToolStart` on the injected `delegate_task` combined with app-defined state, child tool-error hooks, MCP `can` and `onHandoffComplete` already supplies an equivalent version-safe lawful team S3 hold/subset choice, pre-dispatch effect and subsequent feedback; OR child denial cannot be safely correlated or parent ceiling cannot be enforced
- Scenario basis: HYPOTHETICAL
- Proposal-stage decision: GO
- Research disposition: NEEDS_EVIDENCE
- Proposed validation: Same supervisor with read-only Researcher and authorized Writer, an actual MCP write denial and next `delegate_task`: compare native-only `onToolStart` + MCP `can` + callbacks versus proposed typed pre-dispatch decision; test allow/hold/selected-subset, denied child rights escalation, parallel dispatch race, missing callback, stale authorization, and returned handoff feedback; native tests NOT_RUN
- Validation state: NOT_RUN
- Proposal falsifier: Native-only composition already supplies identical effective and returnable team decision, or new callback cannot safely enforce under parallel `handoffToMultiple`; no extra C constructor should be claimed in that case
- S1 disposition: Autonomous Agent model/tool execution with operational feedback; accepted A; no new S1 constructor requested
- S2 disposition: Optional SubAgentManager delegate_task and workflow composition coordinate specialists; accepted C; no extra coordination mechanism requested
- S3 disposition: Accepted historical —; conditional C is a separate team-wide current-control actor able to restrict the next native `delegate_task` based on operational denial feedback, with lawful pre-dispatch effect and later handoff result, not a static per-agent guard or new S5 right
- S3* disposition: Guardrails, hook events and tracing are observations, not a separate independent audit-to-correction actor in this case; NO_TARGET
- S4 disposition: Models, tool integrations, fallback and workflow state do not establish prospective environment intelligence for this scenario; NO_TARGET
- S5 disposition: App owner defines immutable identity, upper tool grants and approval policy; no S5 purpose/identity change delegated; NO_TARGET
- Result: PLAN_ONLY
- External issue: DRAFT — NOT PUBLISHED
- Public fork Issue: DRAFT — NOT PUBLISHED
- Cost status: NOT_MEASURED

## Identity and pins

[Current original source@e9fc599f](https://github.com/VoltAgent/voltagent/commit/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c) was independently checked against the accepted [Index assessment](https://github.com/opensiro/vsm-harness-index/blob/8f436270813b844aafc16917d69bc09661ef1544/assessments/vo/voltagent.md): included, exact original/harness_id/review_ref matched [Index catalog](https://github.com/opensiro/vsm-harness-index/blob/8f436270813b844aafc16917d69bc09661ef1544/data/catalog.psv). The historical six-grade vector and review date are not a current assessment or defect list. The source inspection covered repository boundaries and primary runtime, API/hook, product/docs, testing, CI structure, license and original Issue/PR paths. This is not an exhaustive untested runtime behavioral proof.

## Rights and authority

Original [LICENCE](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/LICENCE) is MIT; [CONTRIBUTING](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/CONTRIBUTING.md) routes to a contributor guide. Formalities/CLA/DCO/AI declaration requirements beyond inspected text are unverified. Verified working fork `opensiro-contributions/voltagent` is a real fork of `VoltAgent/voltagent`; `opensiro/meta` read back `ACTIVE / ALLOW`. Application owner, not a proposed S3 actor, sets the upper bound of tool identity/privileges. Maintainers decide actual product direction. No external/public Issue/PR/comment, third-party patch, product tests or Index regrade authorized by this record.

## Existing work / overlap

- SHIPPED [MCP `authorization.can`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/mcp/authorization.md) provides discovery filtering and per-execution access decisions (original merged [PR #870](https://github.com/VoltAgent/voltagent/pull/870)).
- SHIPPED [hooks](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/hooks/index.ts) expose `onToolStart/onToolEnd/onToolError`, [SubAgentManager](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts) provides `delegate_task`, [ToolManager](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/tool/manager/ToolManager.ts) prepares tools, and [workflows](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/workflows/suspend-resume.md) permit owner-driven pause/resume. These can solve narrower authorized-call tasks and may be a complete cheaper baseline; do not assert every tool path is protected without native tests.
- OPEN [Issue #1177](https://github.com/VoltAgent/voltagent/issues/1177) requests per-agent tool policy, child read-only grants, and audit; original OPEN/UNMERGED [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390) proposes a per-agent `toolGuard` with denied-call callbacks (head `0fb458490703f5a89f6bb0e196c0c4f79bf95cb1`). **Not shipped.** OPEN [PR #821](https://github.com/VoltAgent/voltagent/pull/821) targets traffic concurrency and adaptive limiting, not tool-grant decisions. OPEN [PR #1549](https://github.com/VoltAgent/voltagent/pull/1549) targets retry replay safety.
- Separate [fork-local supervisor commitments case](https://github.com/opensiro-contributions/voltagent/blob/78496f45b5475a42b409eac4b4aa3a396b907836/.opensiro/issues/supervisor-commitment-control-20261119/roadmap.md) already proposes S3=C for team **work admission/budget/commitments**, not authorization. This Wave 4 refinement now restricts the *next* `delegate_task` dispatch after observed denial; tool grants remain app-owned and team budget/commitment admission remains in the separate S3 case. Overlap still requires native tests.

## Function ownership

| Function | Accepted historical state | Current first-party closure and limitation | Wave 4 C priority |
| --- | --- | --- | --- |
| S1 | A | Agent operates model/tools; tool denial is operational feedback | Already A |
| S2 | C | SubAgentManager coordinates optional subagents and handoff | Already C |
| S3 | — | Current rights checks are app-authored per-call boundaries; team-wide feedback-driven *restrictive* action decision is a proposed gap, not a shown feature | **P0 hypothetical S3=C** |
| S3* | — | Hooks/guardrails/telemetry need an independent audit authority to qualify | No target |
| S4 | — | No outside-and-future adjustment scenario established by tool permission checks | No target |
| S5 | — | Operator/application retains identity/upper grant policy and escalation | Parent retained |

Deliberate local S3 omission is **UNVERIFIED**; the owner-controlled S5 boundary is legitimate. No grade change.

## Capability priority

**P0:** opt-in typed decision at `SubAgentManager.createDelegateTool` after target name lookup and before parallel `handoffToMultiple`. Distinct authorized choices are ALLOW, HOLD, a subset of already-selected registered children, and escalation to the owner; results return through native hooks. **P1:** native-only `onToolStart` veto falsifier, child MCP denial attribution, safety/return tests. **P2:** NONE. GO / NEEDS_EVIDENCE is conditional architectural constructibility, not a product priority or a tool grant policy; separate S3 commitments case untouched.

## Parallel contribution-on-top review

| Track | VoltAgent current path | Minimal missing link / qualification | Falsifier |
| --- | --- | --- | --- |
| A · registered delegation | `createDelegateTool` resolves `targetAgents`, then calls `handoffToMultiple` with parallel children | No actor-driven typed pre-dispatch decision exists in inspected source | `onToolStart` on the injected delegate tool may already veto an equivalent scenario |
| A · denial + feedback | MCP `authorization.can` checks execution; child `onToolError` and supervisor `onHandoffComplete` exist | Child MCP denial attribution/parent correlation NOT_VERIFIED; post-handoff hook is after work | Actual native denial might not reach the owner/actor |
| A · proposed native PR | #1390 open/unmerged per-agent `toolGuard`, #821 traffic, #1549 replay | Do not credit these as shipped or confuse tool gate with team S3 | Equivalent first-party C ownership later may supersede this proposal |
| B · new minimal first-party port | Optional `SupervisorConfig` callback after registered-target lookup, before parallel dispatch | Parent-fixed rights; versioned child denial; `allow/hold/selected subset/escalate`; effect and later handoff feedback | If existing native-only callback composition already does this, NO_NEW_C |
| Adjacent existing roadmap | Separate supervisor-commitment S3 case concerns work/budget | No new queue/scheduler or S5 grants here | Deduplicate if a single implementation covers both |

## v0.18.1 native-specific continuation

**Status:** This is a post-patch refinement of the already source-first Wave 4 decision [sealed before historical comparison](https://github.com/opensiro/upstream/issues/58#issuecomment-7043540206), **not** a second blind first attempt. The [native-specific recommendation](https://github.com/opensiro/upstream/pull/87) is advisory, not a new gate, score or maintainer-product veto.

**Concrete VoltAgent task:** a `Supervisor` has registered `Researcher` (read-only) and `Writer` (owner-authorized) `subAgents`. A child attempts a forbidden MCP write; the shipped MCP client [runs `authorization.can` before the call](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/mcp/client/index.ts#L474-L501). When the supervisor next invokes its automatically injected `delegate_task({task,targetAgents,context})`, an app-composed S3 actor would use the earlier attributed denied action and fixed parent policy to HOLD or permit only a subset of the already selected children. No implicit new worker or privileged tool is introduced. A later result informs the next decision.

**Exact first-party insertion point:** [`SubAgentManager.createDelegateTool`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts#L776-L857) resolves strings from `targetAgents` against `subAgentConfigs`, then calls [`handoffToMultiple`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts#L735-L749), which runs them via `Promise.all`. A new optional typed pre-dispatch decision in existing [`SupervisorConfig`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/types.ts#L344-L382) is the candidate minimal port. It must be called and applied **before** parallel dispatch. [`Agent.prepareTools`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/agent.ts#L6331-L6366) already injects `delegate_task` through the ordinary local tool wrapper.

**Most important native falsifier:** [`onToolStart`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/agent.ts#L6478-L6491) already runs before local tool execution, and may be sufficient to veto `delegate_task` with application-owned shared state. Try it first; do not assert a missing first-party constructor without comparing the same hold/subset and later return. [`onHandoffComplete`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts#L470-L496) provides result/usage **after execution**; its exceptions are logged and ignored, hence it is feedback, not a pre-dispatch veto. Whether child `onToolError` delivers a reliably linked MCP denial to the parent is untested. Existing original [Issue #1177](https://github.com/VoltAgent/voltagent/issues/1177) and **open/unmerged** [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390) address per-agent authorization separately.

**Boundary:** Existing application/MCP policy enforces leaf tool permissions. Do **not** build a universal local/provider/MCP gate, assign S5 policy rights to S3, or duplicate [the separate supervisor-commitment S3 case](https://github.com/opensiro-contributions/voltagent/blob/78496f45b5475a42b409eac4b4aa3a396b907836/.opensiro/issues/supervisor-commitment-control-20261119/roadmap.md). This is a falsifiable PLAN_ONLY proposal. Native tests NOT_RUN; benefit NOT_MEASURED.

## Implementation options

No product code is authorized. The narrow P0 would add an optional typed `SupervisorConfig` callback between `targetAgents` lookup and `handoffToMultiple`, using parent-fixed rights and observed child denial for `allow/hold/selected subset/escalate`; later `onHandoffComplete` and linked tool errors close the feedback path. Before any implementation, test whether existing `onToolStart` veto and MCP `can` with an app-local actor already do the same thing. No new global policy DSL, cross-tool middleware, budget scheduler or additional VSM controller. Native tests NOT_RUN.

## Specification and domain alternatives

This is a VSM-informed **S3 current-regulation constructibility experiment**, not a universal access-control requirement. Static per-agent authorization is a separate S1 safety check; no S5 policy issuance, S3* audit agency or S4 prospective environment model is inferred. A parent-owned policy engine or a narrowly scoped original #1177 fix is a legitimate final product choice; that choice is with maintainers. An independently configurable team's *temporary restriction* may be source-native and C-qualifiable even if the product does not adopt it. A future independent Index evaluation, not this proposal, would decide grades.

## Cost experiment

No native execution or matched source test, demonstrated benefit or cost measurement was performed. Future test compares the same Supervisor/Researcher/Writer denied-MCP scenario on shipped hooks plus native MCP `can` versus proposed narrow pre-dispatch port, checking rights, next-dispatch effect and returned feedback. **NOT_RUN / NOT_MEASURED**. Do not introduce a specificity metric or scoring rubric.

## Delivery and publication

- Source-first independent Wave 4 [checkpoint](https://github.com/opensiro/upstream/issues/58#issuecomment-7043540206) and original fork receipt remain historical; this is post-v0.18.1 **same-case** native-specific refinement, not a fresh blind re-run.
- New [continuation claim](https://github.com/opensiro/upstream/issues/58#issuecomment-7044398119). Earlier NO_GO for independent ultimate authorization-policy issuance remains in Git history. Separate S3 budget/commitment proposal remains unchanged.
- Protocol v0.18.1 advisory [PR #87](https://github.com/opensiro/upstream/pull/87); reporting rule merged [PR #89](https://github.com/opensiro/upstream/pull/89). Historical status-only [PR #85](https://github.com/opensiro/upstream/pull/85) was closed unmerged; new per-run Upstream PR or report file is prohibited.
- Structural validator and remote SHA readback required for this revision. Current case draft prepared, **NOT PUBLISHED**. Native tests NOT_RUN, costs NOT_MEASURED, no product implementation, external Issue/PR/comment, fork public Issue or Index regrade.


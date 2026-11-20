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
- Evaluation object: Optional S3 current-operation restriction and hold/reassignment of tool-capable actions across a team under an immutable application-supplied permission ceiling, not an autonomous S5 policy grant or merely an agent-local toolGuard
- Existing-work overlap: SHIPPED MCP authorization can, tool wrappers, hooks, supervisor delegation and workflow suspension; OPEN/UNMERGED original toolGuard PR #1390; distinct pre-existing OpenSiro supervisor-commitment S3 proposal (resource/commitment admission) is not shipped and must not be duplicated
- Our on-top contribution: PLAN_ONLY optional first-party team-scoped S3 decision constructor that receives a versioned active-team action/denial snapshot, chooses only lawful temporary NARROW/HOLD/REASSIGN/ESCALATE options, enforces the decision through local/provider/MCP/delegation boundaries and observes the next action outcome; never widens parent rights
- Incremental benefit: HYPOTHETICAL coherent team-level *dynamic* restriction/return over independent per-agent static authorizers, not a measured need, savings, incident, or maintainer request
- Decision scope: Wave 4 post-release v0.18.0 architecture-only GO for an optional differentiated S3=C construction hypothesis; no product adoption decision, Index regrade, shipped capability or implementation
- Target transition: S3=— -> S3=C
- Priority rationale: S1 is already autonomous and S2 already composable; S3 has a source-mapped team-wide current-state/choice/action/return candidate only if the control is genuinely cross-boundary and not just a policy callback; S3*/S4 lack this case's independent external evidence loop; S5 policy remains parent-owned
- P1 dependencies: Prove action-path coverage on actual core versions, parent immutable upper rights, versioned non-escalating snapshot, race-safe enforcement/compensation at local/provider/MCP and delegate_task entry points, post-decision audit feedback, and tests against shipped source-native baseline and open PR #1390 without treating the latter as merged
- P2 optional: NONE; maintain separate supervisor-commitment S3 case and no coupling to unrelated S4 or S5 work
- Proposed C construction: In an opt-in multi-agent installation, developer composes an S3 actor under explicit owner-set fixed grants; first-party team control port gathers per-agent live grants/denials/in-flight delegation/feedback; actor chooses among several restrictive operational responses; validated atomic action applies to all supported execution paths; next operation feedback closes and corrects the current-control loop
- C sufficiency falsifier: The *shipped* MCP can, local tool wrappers and standard hooks combined with existing supervisor/workflow already provide the same first-party team-level independent state/options/decision, non-bypassable cross-path enforcement and correlated subsequent feedback without adding any constructor port; or no lawful role can perform the claimed independent decision
- Scenario basis: HYPOTHETICAL
- Proposal-stage decision: GO
- Research disposition: NEEDS_EVIDENCE
- Proposed validation: In a multi-subagent fixture with read-only child, privileged supervisor, local/provider and MCP actions, compare static application-owned can/wrappers with the candidate team S3 actor; test allowed action, dynamic narrowing, denial feedback/next choice, privilege escalation refusal, missing actor default, revoked grant race, delegations and workflow resume; execute with native suite in future
- Validation state: NOT_RUN
- Proposal falsifier: Native-only scenario shows identical lawful team-level actor choice, enforcement on all paths and subsequent feedback, or parent rights cannot be enforced without unsafe override; then revise to NO_GO
- S1 disposition: Autonomous Agent model/tool execution with operational feedback; accepted A; no new S1 constructor requested
- S2 disposition: Optional SubAgentManager delegate_task and workflow composition coordinate specialists; accepted C; no extra coordination mechanism requested
- S3 disposition: Accepted —; candidate C only for a distinct, developer-composable team current-operation decision owner with live state, restrictive action and later feedback, beyond stateless per-tool policy
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
- Separate [fork-local supervisor commitments case](https://github.com/opensiro-contributions/voltagent/blob/78496f45b5475a42b409eac4b4aa3a396b907836/.opensiro/issues/supervisor-commitment-control-20261119/roadmap.md) already proposes S3=C for team **work admission/budget/commitments**, not authorization. This Wave 4 design is restricted to **cross-tool execution rights below owner ceiling**, not a second task queue or a new S5 authority. Overlap must be measured, not assumed absent.

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

**P0** optional current-operation team action-right narrowing/hold/reassignment constructor with end-to-end feedback, **not** static authorization middleware. **P1** source-native execution-path/rights integration and testable distinguishability versus existing `can`, hooks, wrappers, and the still-unmerged `toolGuard` PR. **P2** none. Scenario **HYPOTHETICAL**, proposal-stage **GO / NEEDS_EVIDENCE**, not product prioritization or demonstrated ROI. The cheapest native alternative is application-owned authorization and a supervisor-controlled workflow; if it already creates the full team-level C loop, this proposal fails.

## Parallel contribution-on-top review

| Link / track | Current coverage vs proposed minimum | Differentiated actor / closure | Falsifier |
| --- | --- | --- | --- |
| A · shipped baseline | MCP `can`; local wrappers; agent hooks; subagent result forwarding; workflow suspend/resume | App author supplies fixed rules, no demonstrated single first-party cross-path dynamically restrictive team S3 actor | Prototype native-only team actor and show equivalent feedback |
| A · original active proposal | #1390 open toolGuard + denied-call hooks; #821 open rate/traffic and #1549 open replay fix | Proposed agent-local enforcement/transport, **not credited shipped** nor necessarily S3 | If merged unchanged and adequate for whole-team decision/return, extra port not justified |
| B · reusable link | Reuse `can`, hooks, delegation, existing event/trace context, parent role config without changing authorization decisions | A composable independent S3 team state/decision interface with **no expansion of rights** | Same user actions can be achieved by a static wrapper with equal actual S3 ownership |
| B · minimal missing port | A first-party shared/versioned live action-rights snapshot + restrictive multi-path enforcement/feedback seam for developer-composed decision actor, including non-bypassable child dispatch | Distinct choice `keep/narrow/hold/reassign/escalate`, authorized effect on next operation, feedback to next decision | No coherent common enforcement boundary or unavoidable double execution race -> no C |
| Excluded overlapping case | Existing separate supervisor-commitment S3 case governs tasks/budget admission, not tool grants | Keep cases independent, do not double-count same constructor capability | If its actual eventual port already implements action-rights control, dedupe this case |

## Implementation options

No code change now. Before implementation, compare (1) app-supplied stateless `can`/wrapper and documented hooks, (2) finishing original native #1390 without a new controller, (3) opt-in shared team current-control port. Draft only typed interfaces matched to actual original source, not a generic policy DSL. Rights scope cannot allow grants above the parent ceiling; a missing state/controller or stale snapshot must fail closed for protected actions. P1 native tests must cover local tools, provider tool invocation, MCP, delegate_task and resume, plus failure/denial outcome correlation.

## Specification and domain alternatives

This is a VSM-informed **S3 current-regulation constructibility experiment**, not a universal access-control requirement. Static per-agent authorization is a separate S1 safety check; no S5 policy issuance, S3* audit agency or S4 prospective environment model is inferred. A parent-owned policy engine or a narrowly scoped original #1177 fix is a legitimate final product choice; that choice is with maintainers. An independently configurable team's *temporary restriction* may be source-native and C-qualifiable even if the product does not adopt it. A future independent Index evaluation, not this proposal, would decide grades.

## Cost experiment

No matched execution, native suite, security test, cost estimate, slowdown or user-demand measurement was performed. A future apples-to-apples fixture should compare same team/commands/roles/denials with shipped baseline and proposed bounded team actor; measure tests, implementation/maintenance, latency, privilege leakage and decision-to-return observability. **NOT_RUN / NOT_MEASURED.**

## Delivery and publication

- **First-pass sealed** at [#58 checkpoint](https://github.com/opensiro/upstream/issues/58#issuecomment-7043540206) before inspecting prior case argument.
- **Historical comparison afterward:** preceding `tool-authorization-native-overlap-20261119` recorded **NO_GO / NO_USEFUL_CHANGE** for an autonomous S3/S5 policy chooser; it rejected unsupported new **ultimate policy** authority and unmeasured practical need. Wave 4 does **not** claim policy authority: it hypothesizes *bounded current-operational restriction* with parent-fixed rights. This distinction is the scoped reason for current **GO / NEEDS_EVIDENCE**, not a claim the previous review was wrong for its earlier scope; earlier commits remain immutable. Separate `supervisor-commitment-control-20261119` S3 GO stays unchanged.
- Structural validation: pending native `scripts/validate_capability_roadmap.py` for complete Human/AI/receipt; final readback must be verified separately.
- Research and product: `PLAN_ONLY`, native tests `NOT_RUN`, benefit `NOT_MEASURED`. No implementation or product adoption.
- Public fork Issue: **NOT_PUBLISHED**, existing draft untouched; external original Issue/PR/comment: **NOT_PUBLISHED**. No third-party communication.

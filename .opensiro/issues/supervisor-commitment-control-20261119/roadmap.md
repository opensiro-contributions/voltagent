# VoltAgent — independent six-function roadmap receipt: shared current commitments

## Identity and pins

- Original repository: VoltAgent/voltagent
- Original HEAD: e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c
- Observed at: 2026-11-19
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/b6318e9fb855c20a0a48dfd0ea03f78aaafbb320/assessments/vo/voltagent.md
- Accepted assessment blob SHA: c7dec10ee48c461833c33e0ceb408cd49ed57fdd
- Accepted review ref: 44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de
- Accepted reviewed at: 2026-09-19
- System in focus: One installed first-party VoltAgent application with Agent, two or more specialist subagents, SubAgentManager, supported hooks, memory and workflows. External model services, user-defined business rules, separately operated VoltOps, and maintainer governance are excluded.
- Index commit: b6318e9fb855c20a0a48dfd0ea03f78aaafbb320
- Index catalog: https://github.com/opensiro/vsm-harness-index/blob/b6318e9fb855c20a0a48dfd0ea03f78aaafbb320/data/catalog.psv ; harness_id voltagent, original exact, review_ref exact.
- Profile / Methodology: 0.2.3 / 0.3.5, historical and not regraded.
- Independent protocol: https://github.com/opensiro/upstream/blob/be03ced5ed5d3b7210762df612dc4b3f452c1a73/docs/ROADMAP_INDEPENDENT_RERUN.md, v0.18 main.
- Receipt contract: proposal-gate
- Accepted VSM vector: S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—
- Target transition: S3=— -> S3=C
- Scenario basis: HYPOTHETICAL
- Proposal-stage decision: GO
- Research disposition: NEEDS_EVIDENCE
- Validation state: NOT_RUN
- Result: PLAN_ONLY
- External issue: DRAFT — NOT PUBLISHED
- Cost status: NOT_MEASURED

Historical assessment reviewed 61 days earlier, at a different original commit; source drift is material to any new Index-owned grade, but no grade is inferred here. Source link: https://github.com/VoltAgent/voltagent/commit/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c.

## Rights and authority

- MIT license verified from original LICENCE and core package.json; original [contributor guide](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/community/contributing.md) prescribes pnpm tests, changesets and PR review. No claim that a human CLA/DCO/AI declaration is waived or that the original maintains interest in this proposal (NOT_STATED).
- Verified working fork: opensiro-contributions/voltagent; actual GitHub fork=true, parent VoltAgent/voltagent, distinct opensiro/meta branch; owner state read back 2026-11-19 ACTIVE / ALLOW after attributed issue #58 activation event 20261119T182226Z--owner-upstream58-active.
- The application owner defines a bounded team commitment/budget envelope and permitted options. The composed S3 actor may only arbitrate within those limits, never grant permissions, access more tools, replace human approvals or revise S5 policy.
- Internal case persistence only. No public fork Issue/PR, external comment/PR, code implementation, release, test success or maintainer acceptance is authorized or claimed.

## Existing work / overlap

- SHIPPED S1 and S2: [Agent/subagent supervisor](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts) with developer-registered subagents, generated delegation tool, model-chosen routing and later handoff result. The [docs](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/subagents.md) describe optional multi-specialist mode; simple Agent applications do not contain the proposed team.
- SHIPPED hook/usage path: [hooks](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/hooks.md) expose onHandoffComplete result/usage, onEnd usage and onTool* callbacks; [SubAgentManager](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts) has per-agent maxSteps and returns per-handoff usage, but does not enforce an atomic shared portfolio of task commitments with a separately composed current-management decision owner.
- SHIPPED alternatives: user can set maxSteps and custom supervisorConfig, choose a simpler sequential workflow, use application-defined queue/budget logic, or keep human allocation. [Workflow suspend/resume](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/workflows/suspend-resume.md) supports caller-controlled continuation; not autonomous whole-team current management by itself.
- OPEN_PR [#821](https://github.com/VoltAgent/voltagent/pull/821), head ef8fd5c3397a1ca8c8dc785c9b999cbf66650e54: unmerged traffic admission/concurrency, priority, usage and adaptive limiter implementation in core; diff for traffic-controller.ts and traffic-usage-tracker.ts inspected. This may substantially subsume the required scheduling/usage mechanisms, but a request-level traffic controller is not automatically a developer-composed organization-wide S3 actor with task commitments and decision return.
- OPEN_PR [#1475](https://github.com/VoltAgent/voltagent/pull/1475), head 6db524e1686fc13760c27c2070ba7bd159f40890: generated-object handoff result correctness, not current commitment allocation. CLOSED_MERGED [#1372](https://github.com/VoltAgent/voltagent/pull/1372): final-step and aggregate AI SDK usage in hooks; useful native return signal, not S3 itself.
- OPEN original [#1177](https://github.com/VoltAgent/voltagent/issues/1177) and OPEN_PR [#1390](https://github.com/VoltAgent/voltagent/pull/1390), head 0fb458490703f5a89f6bb0e196c0c4f79bf95cb1: per-agent tool permission guard. OPEN_PR [#1219](https://github.com/VoltAgent/voltagent/pull/1219): generic execution validators. Both are different authorization/validation work; do not duplicate or relabel as S3.
- OPEN_PR [#1541](https://github.com/VoltAgent/voltagent/pull/1541) and [#1549](https://github.com/VoltAgent/voltagent/pull/1549) address persistence/replay reliability, not team-level priority decisions. Related Issues #1538 and #1537 are not evidence of a shared-budget user incident.
- Native tests / CI: packages/core uses vitest, typecheck and build; native tests NOT_RUN; remote PR authors' self-reported results not independently reproduced.

## Function ownership

- S1 disposition: Historical A; model-directed tool execution and returned outcomes remain the operational units; no proposed S1 C intervention.
- S2 disposition: Historical C; developer-composed supervisor forwards/delegates work and synthesizes specialist results; preserve coordination, not force another coordinator.
- S3 disposition: Historical —; current supervisor's task routing and local maxSteps do not demonstrate an installed team-wide current commitment allocator. P0 candidate: bound one developer-composed independent decision owner to shared commitments, lawful operational effect and returned consequences.
- S3* disposition: Historical —; output guardrails, observability, evals and callbacks do not themselves demonstrate a separate independent complementary audit right at the chosen team boundary. No justified S3* P0; if independent audit is required later it needs its own scope and tests.
- S4 disposition: Historical —; dynamic model/tool configuration and model fallbacks help current operation but no source-grounded future/external adaptation task with a complete new S4 actor is established by this use case.
- S5 disposition: Historical —; developer/application owns identity, budgets, permissions and approval policy outside runtime autonomy. This legitimate parent boundary must not be reclassified as a defect or delegated to S3.

## Capability priority

- Repository-wide source map: Runtime Agent/subagent, optional PlanAgent, hooks, memory persistence, guardrails, workflow suspend/resume, core tests and TS package scripts, docs, contributors and original Issues/PRs screened at pinned main. No separate VoltOps/cloud claims credited to in-boundary OSS runtime.
- Priority rationale: S3 current commitments is narrower and technically testable on top of shipped S2 delegation and usage hooks, without duplicating local tool authorization, S1 retry repairs, S3* evidence scoring, hypothetical S4 or parent S5.
- P0: Propose a first-party developer-configurable S3 current-commitment controller for a multi-subagent team that selects admit/defer/reassign/hold from live authorized project state, atomically applies the choice before delegation, and receives linked later task/usage feedback.
- P1 dependencies: Inspect #821 final PR head and owner disposition before engineering; model real shared-team budget/commitment collision with an app-defined envelope; secure idempotent/version-guarded reservations, cancellation/release and parent rights at subagent dispatch; compare simplest manual queue and approved traffic limiter.
- P2 optional: NONE. Do not couple toolGuard, S3* or provider S4 work into this proposal.
- Proposed C construction: Reuse [SubAgentManager](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts), existing [usage/handoff hooks](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/hooks.md) and existing workflow/parent boundaries; add only first-party admission/commitment snapshot + developer-supplied autonomous manager decision port, atomic application to specialist dispatch and linked completion feedback to manager and supervisor. Provide a strict no-manager behavior preserving native control, not an implicit hardcoded manager.
- C sufficiency falsifier: If #821 or application-native queue already delivers equivalent lawful team commitment choices and feedback with less cost, or no first-party atomic dispatch/return bridge can be built without overriding parent rights, then reject the extra S3 constructor.
- Proposed validation: Two specialist tasks share a declared limited resource; autonomous composed owner observes current commitments, chooses admit/defer/reassign/hold, first-party dispatch enforces the decision, and completion/failure/usage is returned with stable task identity. Repeat with different lawful owner decisions and parent limits; measure against native sequential/traffic-controller baseline.
- Proposal falsifier: If a fixed queue or static maxSteps yields the same operator outcome on matched tasks, or enforcement is bypassable/stale and manager feedback is only advisory, the proposed C transition is false.

## Parallel contribution-on-top review

- Evaluation object: Team-level current resource and commitment selection among simultaneously delegated specialists in a first-party VoltAgent application, distinct from generic tool authorization.
- Existing-work overlap: SHIPPED subagent delegation, hooks, maxSteps, workflow; OPEN unmerged traffic PR #821 may already provide scheduler and counters; no proof of existing complete S3 choice/authority/return actor.
- Our on-top contribution: A separately developer-installed, first-party S3 decision port over current cross-agent obligations, guarded dispatch/release and operational feedback, designed to reuse #821 if its eventual accepted interface suffices.
- Incremental benefit: HYPOTHETICAL — permit bounded policy-dependent allocation of scarce team resources instead of relying only on opportunistic model delegation or static queue; no measured advantage or real user demand asserted.
- Decision scope: Proposal GO for a source-grounded construction hypothesis, not GO to implement, publish externally, claim saved cost or change historical grades.

## Implementation options

1. Reuse no new S3: manually cap concurrent workflows, use per-agent maxSteps and supervisorConfig. This remains safest until a real shared-commitment scenario is validated.
2. Reuse accepted #821 if merged: traffic queue/priority/usage under its own operational boundary. Compare current task and team commitment needs before proposing any extra integration.
3. Preferred proposed S3=C: a scoped actor and first-party enforcement/return seam in the existing delegation pipeline; no standalone scheduler service if the native core suffices. All proposals NOT_IMPLEMENTED.
4. No parallel auth guard: keep #1177/#1390 in their owning native review; do not propose S5 delegation.

## Specification and domain alternatives

No Profile/Skills method defect established; pursue separate methodology feedback only if a genuine mapping counterexample appears. A legally permitted domain fork is an optional independent experiment, not an automatic external PR or an operational mandate.

## Cost experiment

Compare the same two-agent resource-conflict task under native sequential/manual control, #821 if available, and constructed S3; record setup, API integration, runtime overhead, denied/held outcomes, reviews/tests and maintenance. Cost status NOT_MEASURED; native tests NOT_RUN.

## Delivery and publication

- Human decision: [issue.md](issue.md)
- AI contract: [constructor-sufficiency.md](constructor-sufficiency.md)
- Case readme: [README.md](README.md)
- Issue draft: [fork-issue-draft.md](fork-issue-draft.md)
- Historical distinct case preserved at ../tool-authorization-native-overlap-20261119/roadmap.md: old NO_GO for optional S3/S5 tool authorization control; not a refutation of this narrower independent S3 commitment hypothesis.
- Current outcome: GO / NEEDS_EVIDENCE / PLAN_ONLY; expected native tests NOT_RUN; measured benefit NOT_MEASURED; result PERSISTENCE_PENDING until exact metadata commit/readback.
- No public fork GitHub Issue or PR, original Issue/comment/PR, product code, CI run, accepted Index change or implementation claimed.

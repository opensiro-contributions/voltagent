# VoltAgent — AI/developer first-party S3 constructor sufficiency contract

**Level 2 PLAN_ONLY · HYPOTHESIS → proposal GO → future tests.**
**Human decision:** [issue.md](issue.md). **Canonical source:** [roadmap.md](roadmap.md).
**Target transition:** S3=— -> S3=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

## Scope and independent review boundary

The historical six-function vector and source pins live in [roadmap.md](roadmap.md); do not regrade. Current implementation target is [SubAgentManager](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts) in installed @voltagent/core, one supervisor and two specialists, no external managed VoltOps, no third-party tool/memory rights, no application-wide authority claims. Track A first-party supervisor chooses specialist(s), executes handoffs, reports usage/result to parent onHandoffComplete, and has per-agent maxSteps. This is S2 coordination, not verified S3 portfolio choice.

S1 operations retain action authority; S2 delegates; S3 prospective actor gets only defined current resource/commitment arbitration; S3* independent audit remains separate and not presumed from guardrails; S4 external-future planning not constructed; S5 application developer sets limits and may veto. Counterfactual owner test: remove proposed developer-installed manager and the normal supervisor, tools and human queue still run, but *no separate composed team-wide adaptive commitment choice* occurs.

## Source-pinned parallel A/B examination

| S3 link | A: shipped and native overlap | B: minimal construction, not a shipped claim | Falsifier |
| --- | --- | --- | --- |
| Trigger and state | [SubAgentManager](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts) accepts task/target, returns usage; [hooks](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/hooks.md) provide onHandoffComplete; #821 OPEN traffic queue/counters | Project-scoped, versioned team commitments/capacity snapshot, eligible operation types and parent-bounded options exposed before delegation | Current traffic controller or app queue already exposes all required state and lawful choices |
| Autonomous decisive owner | Supervisor prompt/LLM picks specialists, but there is no verified independent current portfolio controller | Optional developer-installed function-specific S3 actor chooses one of admit/defer/reassign/hold with reason and task/revision identity, constrained by configured parent policy | Actor is only a notification, fixed queue, hidden parent-only decision or an unjustified permission escalator |
| First-party effect | [handoffTask](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts) invokes target agent and may forward error text; currently no first-party shared reservation gate | Before delegate_task execution enforce chosen decision through atomic reserved active commitment slot; deny/release on stale, policy veto, cancellation or failure | Side effects occur before enforcement; stale choices can run; no supported place to enforce without changing unrelated subsystems |
| Closed return | onHandoffComplete is called with result and usage, plus parent spans | Link actual target task result/usage/error to commitment receipt and manager/supervisor; reconcile release; persist only as configured and bounded | Feedback is trace-only, never reaches manager or suppresses failure |

### Source-native alternatives actively compared

1. **No new runtime port:** application-level work queue and supervisorConfig/maxSteps + onHandoffComplete reporting, acceptable if enough.
2. **Reuse #821 if merged and admitted:** it already has priority, queue/concurrency, adaptive signals and usage tracking (open PR head ef8fd5c3397a1ca8c8dc785c9b999cbf66650e54; traffic-controller/usage-tracker diffs inspected). Challenge whether its traffic decisions already satisfy the entire scoped S3 witness; do not duplicate its scheduler.
3. **Small S3 control seam in existing subagent dispatch:** optional owner injection, versioned decision and effect, later feedback; no separate infrastructure or hard-coded new organizational manager. Choose only if Track A cannot already express the same lawful independent choice.

[Open toolGuard #1390](https://github.com/VoltAgent/voltagent/pull/1390), [executionValidators #1219](https://github.com/VoltAgent/voltagent/pull/1219) are per-action security/validation and must not be relabeled. [Open #1475](https://github.com/VoltAgent/voltagent/pull/1475) fixes handoff payload, not S3. [Merged hook usage #1372](https://github.com/VoltAgent/voltagent/pull/1372) is helpful for post-decision return.

## Minimal design and authority

**Actor:** application-developer-supplied callback/interface of one installed autonomous S3 agent, not an unconditional built-in manager. **Inputs:** bounded current active/project commitments, stable task ID, budget units, remaining capacity, priority and parent-approved options. **Choices:** admit, defer, hold, reassign to eligible specialist; returning decision token/revision. **Effect:** first-party atomic reservation and version check before calling target Agent. **Closure:** child completion/cancel/error and usage receipts are linked to a reservation and returned to the actor as well as supervisor; state reconciled. **Parent policy:** hard cap, allowed target set, permission envelope and audit visibility stay app/human-owned, with no S5 power delegated.

Critical design challenge: need a compare-and-swap or equivalent single-process guarded ledger and a well-documented process/distributed limitation; claiming exactly-once or multi-host safety without an actual shared store would be false. Use a native supplied/authorized store only where supported. A purely prompt-mediated supervisor decision is S2, not this S3 test.

## Proposed native acceptance

- **Native command:** pnpm test --scope @voltagent/core (documented in first-party contributing guide); package local tests include packages/core/src/agent/agent.spec.ts and subagent tests. Commands NOT_RUN; no environment/dependency install executed.
- **Positive:** deterministic fake two-specialist concurrent tasks, one shared capacity unit, parent envelope and separately composed actor choosing admit/defer, enforced before child dispatch; follow a second choice reassign/hold and verify later result + usage returned with same task id.
- **Negative:** no actor falls through to shipped baseline; stale CAS, unauthorized choice, exhausted budget, cancelled/in-flight task and failed child execution cannot create phantom completion or execute blocked work; no parent policy override.
- **Counterfactual:** same task and constraints run with static sequential queue/maxSteps; then with #821 if merged. Compare equivalent operational outcomes and added engineering, integration, test/review and maintenance cost.
- **Failure criterion:** no genuine actor-owned team-wide decision, only advisory feedback, bypassable dispatch, or equivalent smaller native queue → no sufficient C witness. No automatic Index state mutation.

## Dependencies and stopping

**P0:** optional composed S3 manager plus enforceable current commitment and return path, only if justified.
**P1:** current #821 readback and minimal prototype; explicit app/parent rights; a reproducible legitimate multi-agent conflict, bounded native positive/negative tests.
**P2:** NONE.

Stop on native equivalent C, unsound trust/synchronization, missing lawful app bounds or maintainer rejection. Stage is proposal GO / NEEDS_EVIDENCE, not implementation; no external Issue/PR, product patch, tests, cost metric or accepted C assessment produced. Rights and historical comparison remain in [roadmap.md](roadmap.md). AI-assisted draft, not a substitute for native code review.

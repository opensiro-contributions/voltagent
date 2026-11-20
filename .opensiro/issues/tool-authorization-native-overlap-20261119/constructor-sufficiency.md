# VoltAgent — S3 team execution-rights constructor sufficiency (Wave 4)

**Level 2 / AI technical hypothesis (PLAN_ONLY, not code).**

**Target transition:** S3=— -> S3=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

[roadmap.md](roadmap.md) (canonical source of truth) · [issue.md](issue.md) (one six-function matrix) · [sealed first pass](https://github.com/opensiro/upstream/issues/58#issuecomment-7043540206).

## Source-native boundary

Original `VoltAgent/voltagent` [main@e9fc599f](https://github.com/VoltAgent/voltagent/commit/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c). Historical included Index [assessment](https://github.com/opensiro/vsm-harness-index/blob/8f436270813b844aafc16917d69bc09661ef1544/assessments/vo/voltagent.md) is `A C — — — —`, blob `c7dec10ee48c461833c33e0ceb408cd49ed57fdd`, review `44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de` (Profile 0.2.3, Skills 0.3.5); no regrade. Credited runtime: Agent, optional supervisor/subagents, workflows, first-party MCP and tool execution; cloud VoltOps, external policy engines and project maintainer processes excluded.

## Existing Track A (shipped vs pending)

1. [`packages/core/src/tool/manager/ToolManager.ts`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/tool/manager/ToolManager.ts) wraps local tool execute and handles provider tools; [agent.ts](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/agent.ts) handles execution context and hooks. [hooks](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/hooks/index.ts) report `onToolStart`, `onToolEnd`, `onToolError`; their existence is not proof of synchronized non-bypassable team control.
2. [`authorization.can`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/mcp/authorization.md) already supports discovery and execution checks over MCP; merged original [PR #870](https://github.com/VoltAgent/voltagent/pull/870). Caller-provided rules are parent policy, not a first-party S3 owner.
3. [`SubAgentManager`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts) provides `delegate_task`, [workflows](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/workflows/suspend-resume.md) permit human/caller resume and approval. Neither proves a versioned cross-agent control decision.
4. Original [Issue #1177](https://github.com/VoltAgent/voltagent/issues/1177) OPEN seeks agent-based tool permissions; [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390) OPEN/UNMERGED adds proposed `toolGuard` path; do not credit it to shipped main or infer test success from its test plan. [PR #821](https://github.com/VoltAgent/voltagent/pull/821) OPEN handles traffic admission/rate control, a different S3 experiment; [PR #1549](https://github.com/VoltAgent/voltagent/pull/1549) OPEN handles tool replay.

## Independent Track B — minimal complete S3 C chain

| C link | Source to reuse | Missing first-party connector (HYPOTHETICAL) | Evidence/falsifier |
| --- | --- | --- | --- |
| Joint current state | operation IDs, tool outcomes and agent handoff events | Team snapshot of active child identities, allowed tool ceiling, in-flight operations and versioned denials | Ensure snapshot reflects same team under races |
| Decision options | parent-defined policies, workflow hold, supervisor dispatch | Opt-in S3 actor port choosing `keep/narrow/hold/reassign/escalate`; forbid grant expansion | Two different authorized decisions under same permission ceiling |
| Operational effect | local tool execution adapter, MCP `can`, subagent delegation, workflow resume | One validated restrictive enforcement barrier across local/provider/MCP/child paths | A disallowed child cannot bypass via alternative tool type or race |
| Return and feedback | `onToolError/onToolEnd`, `onHandoffComplete`, trace/operation IDs | Correlate the actor decision with later authorization and task outcomes; revise next decision | No feedback or no consequence -> not C |

This is **not** an autonomous S5 policy issuer. The app must supply immutable `maxRights`; the independent actor has only restrictive operating decisions. It cannot alter identity, elevate grants or waive external human approval. If implementation requires changing ultimate policy, the proposal is invalid.

**Residual versus existing separate S3 case:** [supervisor-commitment-control](https://github.com/opensiro-contributions/voltagent/blob/78496f45b5475a42b409eac4b4aa3a396b907836/.opensiro/issues/supervisor-commitment-control-20261119/roadmap.md) allocates tasks/resources. Do not make this another admission queue. Only a genuinely distinct cross-tool **restrictive rights** decision + enforcement/feedback can qualify. If the future commitment controller subsumes these rights, merge analysis/dedupe rather than creating two runtime controllers.

## Native test contract (future, NOT_RUN)

- **Positive:** parent grants supervisor admin and child read-only; child read succeeds. After a team-level live denial event, S3 actor narrows future permissible child action; actual next action respects the narrower mode and its result reaches the actor.
- **Distinct choice:** with the same upper parent policy, alternative available current-state evidence yields hold or reassign; record why, enforce before delegated execution and observe later result.
- **Negative non-escalation:** actor requests `grantAdmin` or child attempts local, provider or MCP privileged operation; first-party boundary rejects without side effect. Child cannot replay through another transport or workflow resume.
- **Failure:** absent actor, stale state version, denied MCP after discovery, malformed identity, concurrent revocation or controller failure must not silently widen access. No guarantee claimed without native tests.
- **Matched baseline:** run identical team/roles/tools with *shipped* `can` and wrappers + hooks + supervisor. If a single app-level component already realizes identical first-party independent decision ownership, all-path effect and feedback, no new constructor link remains: revise `GO` to `NO_GO`.
- **Sources/legality:** inspect exact tool/hook/provider implementation and original PR heads again before any implementation; MIT license checked; contributor/CLA/AI formalities and publication authority separately gated.

## Decision and attribution

Independent first-pass `GO / NEEDS_EVIDENCE` was sealed in [#58](https://github.com/opensiro/upstream/issues/58#issuecomment-7043540206) before reading the old fork-local arguments. Old same-case `NO_GO` assumed an autonomous new S3/S5 authorization-policy chooser; this Wave 4 proposal is bounded restrictive *current* management with explicit subsequent feedback, not a claim the old decision was defective. The old case is preserved by Git history, and separate S3 resource case remains unchanged.

**Validation status:** native tests NOT_RUN; structural validator required separately; costs NOT_MEASURED. **No third-party/public fork issue, original issue/PR/comment, product implementation, or Index grade change.** Maintainers decide whether any proposed architecture should be built.

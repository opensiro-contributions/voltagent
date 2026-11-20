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

**HYPOTHETICAL concrete case:** `Supervisor` has registered `Researcher` (read-only) and `Writer` (owner-approved). After a denied MCP write by Researcher, a developer-composed S3 actor evaluates the supervisor's *next* `delegate_task({task,targetAgents,context})`; it can ALLOW, HOLD, restrict to an already selected/registered subset, or escalate to the app owner, never add a privileged worker or grant tools.

| C link | Native source | Missing source-native decision seam | Falsifier |
| --- | --- | --- | --- |
| Current evidence | `onToolError` has child Agent/context; `onHandoffComplete` returns child result and usage | Correlate actual `MCPAuthorizationError` to parent handoff and parent-owned role ceiling; **UNVERIFIED** | Denied MCP call not attributable |
| Independent choice | `SupervisorConfig` and registered `subAgents`; `delegate_task` accepts `task,targetAgents,context` | Optional typed composed S3 decision after name lookup: allow/hold/selected subset/escalate | Existing `onToolStart` already handles equivalent owner decision |
| Enforce | `createDelegateTool` directly calls parallel `handoffToMultiple` | Verify and apply choice *before* Promise.all child dispatch; no new targets or rights | Race/bypass or no lawful pre-dispatch effect |
| Return | `onHandoffComplete` after child run, `onToolError` on tool failures | Link the next result/error with earlier S3 choice and reconsider following handoff | Post-factum notification only, no consequential next decision |

**Precise anchors:** [`createDelegateTool`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts#L776-L857), [`handoffToMultiple`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts#L735-L749), [`SupervisorConfig`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/types.ts#L344-L382), [`Agent.prepareTools`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/agent.ts#L6331-L6366), [`onToolStart`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/agent.ts#L6478-L6491), [`onHandoffComplete`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts#L470-L496), [`MCPClient.callTool`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/mcp/client/index.ts#L474-L501).

**Existing native baseline is a real falsifier:** the injected `delegate_task` is a local tool whose `onToolStart` runs before execute. Verify whether an app-local actor can safely hold/subset/retry via this hook with equivalent feedback; do not invent a missing constructor. `onHandoffComplete` runs only *after* work and swallows callback failures, so it is not a gate. Cross-tool universal enforcement is **NOT** part of this minimum P0. Original [Issue #1177](https://github.com/VoltAgent/voltagent/issues/1177) and OPEN/unmerged [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390) concern agent-local tool rights. Separate S3 commitments case controls task budgets; do not duplicate.

## Native test contract (future, NOT_RUN)

- Native-only baseline: supervisor `onToolStart` on `delegate_task`, child `onToolError`, parent `onHandoffComplete`, MCP `authorization.can`; reproduce a denied MCP write and a following delegation, checking independent current-owner choice, enforceable hold/subset and returned feedback.
- Positive proposed port: after registered-target lookup, controller returns HOLD and no child starts; allow returns normal handoff/result; selected subset runs only preselected authorized agents.
- Negative: no unregistered child, elevation of local/MCP rights, stale decision, missing actor in protected mode, concurrent subset bypass or silent execution after controller error.
- Falsifier: shipped hooks already close same lawful S3 decision/effect/feedback, or denied MCP event lacks reliable correlation; then rescind/qualify GO rather than implementing generic machinery.
- Native tests NOT_RUN, costs NOT_MEASURED, no product code or public communication.

## Decision and attribution

Independent first-pass `GO / NEEDS_EVIDENCE` was sealed in [#58](https://github.com/opensiro/upstream/issues/58#issuecomment-7043540206) before reading the old fork-local arguments. Old same-case `NO_GO` assumed an autonomous new S3/S5 authorization-policy chooser; this Wave 4 proposal is bounded restrictive *current* management with explicit subsequent feedback, not a claim the old decision was defective. The old case is preserved by Git history, and separate S3 resource case remains unchanged.

**Validation status:** native tests NOT_RUN; structural validator required separately; costs NOT_MEASURED. **No third-party/public fork issue, original issue/PR/comment, product implementation, or Index grade change.** Maintainers decide whether any proposed architecture should be built.

**v0.18.1 specificity revision:** [patch #87](https://github.com/opensiro/upstream/pull/87) is advisory; status-only [PR #85](https://github.com/opensiro/upstream/pull/85) closed under [PR #89](https://github.com/opensiro/upstream/pull/89). Earlier source-first verdict/history remains intact.

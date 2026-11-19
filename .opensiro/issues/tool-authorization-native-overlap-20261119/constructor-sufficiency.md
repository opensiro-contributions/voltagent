# VoltAgent — AI/developer sufficiency contract, repeated tool-authorization NO_GO

**Level 2 / AI.** Source-pinned bounded recheck, non-blind repeat; not independent clean-room verification.

**Target transition:** `NO_QUALIFIED_C_TARGET`
**Proposal-stage decision:** `NO_GO`
**Research disposition:** `NO_USEFUL_CHANGE`

[roadmap.md](roadmap.md) · [issue.md](issue.md) · [source issue #1177](https://github.com/VoltAgent/voltagent/issues/1177) · [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390)

## Pinned boundary and exact contract

- Original source: `VoltAgent/voltagent` `main@e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c`.
- Accepted Index: [included assessment](https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/assessments/vo/voltagent.md), file blob `c7dec10ee48c461833c33e0ceb408cd49ed57fdd`, `review_ref=44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de`, observed historical date 2026-09-19, Profile 0.2.3, Methodology 0.3.5.
- Declared system: installed VoltAgent core Agent and optional subagent composition, workflow/hook and MCP authorization; external MCP servers, policy engines, VoltOps and maintainer policy excluded.
- Goal: deny unauthorized local/provider/MCP tool execution for less-privileged subagents; retain actual error/audit signals without taking role authority away from application.
- Primary shipped input: [MCP authorizer](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/mcp/authorization.md) `can`, `filterOnDiscovery`, `checkOnExecution` (merged PR #870).
- Native pending overlap: [#1390](https://github.com/VoltAgent/voltagent/pull/1390) OPEN, head `0fb458490703f5a89f6bb0e196c0c4f79bf95cb1`, proposals in `agent.ts` and Agent types add `toolGuard` and `ToolDeniedError`; hooks `onToolError/onToolEnd` report a denial. No merged implementation or executed test inferred.
- Scope-sensitive adjacent PRs: [#821](https://github.com/VoltAgent/voltagent/pull/821) OPEN traffic control, [#1549](https://github.com/VoltAgent/voltagent/pull/1549) OPEN retry replay safety. Do not repackage these into new authority.

## Decision/closure trace

1. Operational actor: current Agent executes tools in response to user and environment (S1).
2. Delegated workers: SubAgentManager may route/intermediate specialized subagents (S2).
3. Existing authorization: the **application** supplies role/identity and `can`/tool wrapper decisions; the framework runs the checks and returns failure or hook events.
4. Hypothetical extra C: must have independent decision actor, legal role/parent policy authority, a *genuinely different* organizational option, enforceable scope and later feedback. No qualifying current source or user outcome for this.
5. Therefore `NO_QUALIFIED_C_TARGET`; a policy enforcement hook must not be relabeled autonomous S3, independent S3* or ultimate S5.

## On-top sufficiency matrix

| Candidate | First-party port / additional logic | Positive test / negative falsifier | Outcome |
| --- | --- | --- | --- |
| Reuse unchanged | Configure MCP `can` and app-authorized local wrappers | MCP tool list filtered and execute denied; no extra C | REUSE |
| Native integration | Original PR #1390 `toolGuard` before tool execution; preserve hooks | Allowed tool executes; denied local/provider tool does not execute; reason and identity logged; no bypass | SOURCE_NATIVE_DEPENDENCY |
| Extra C policy controller | New authority-bearing actor chooses policy across child Agents and reports later work | Distinct authorized branch and operational return, not a wrapper over `can`; none evidenced | REJECT / NO_GO |
| Optional S3 resource manager | Separate v0.18 supervisor-commitment case | Distinct shared current commitments; cannot grant tool permissions | OUT_OF_SCOPE |

## Validation and stop conditions

Proposed acceptance matrix: (1) visible vs hidden tools; (2) MCP check on each call; (3) authorized local/provider execution; (4) denied local/provider execution with callback; (5) delegated worker privilege cannot widen; (6) stale/revoked identity or policy denies; (7) audit includes denied tool, agent identity and reason; (8) retry does not rerun denied/side-effectful work; (9) missing policy fails closed per application contract. **Native tests: NOT_RUN**; cannot claim first-party tests pass. This analysis has NOT implemented code and is not a new Index grade.

Stop if: parent rights are unavailable, a proposed additional C lacks a separate legitimate decision and later return, current first-party PR already covers the outcome, or original maintainer approval/publication gate is missing. The stronger hypothetical requires a real operator reproduction and native-vs-C cost/behavior comparison.

## Attribution and follow-up

The original historical NO_GO is preserved in Git history. The new source-first recheck reaches same scoped NO_GO, but previous case content was seen during intake, so strict fresh-context independent first attempt is **not claimed**. Separate [S3 supervisor case](https://github.com/opensiro-contributions/voltagent/blob/opensiro/meta/.opensiro/issues/supervisor-commitment-control-20261119/roadmap.md) remains GO / NEEDS_EVIDENCE, untouched. Internal metadata permission ACTIVE/ALLOW; no public fork or external-original publication.

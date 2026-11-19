# VoltAgent — repeated NO_GO capability-roadmap source-first recheck (v0.18 contract)

- Receipt contract: proposal-gate
- Original repository: VoltAgent/voltagent
- Original HEAD: e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c
- Observed at: 2026-11-20
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/assessments/vo/voltagent.md
- Accepted assessment blob SHA: c7dec10ee48c461833c33e0ceb408cd49ed57fdd
- Accepted review ref: 44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de
- Accepted reviewed at: 2026-09-19
- Index corpus pin: c2e43bf4750841277b3e58d8ba80314121734764
- Accepted Profile version: 0.2.3
- Accepted Methodology version: 0.3.5
- Accepted VSM vector: S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—
- System in focus: First-party VoltAgent @voltagent/core Agent, MCP tool authorization, per-agent tool execution, optional supervisor/subagents and supported workflow/hook surfaces; external policy engines, MCP servers, separately operated VoltOps and maintainer governance are outside the runtime boundary
- Repository-wide source map: original LICENCE and contributing guide, packages/core/src/agent/types.ts, packages/core/src/agent/subagent/index.ts, website/docs/agents/mcp/authorization.md, website/docs/agents/hooks.md, website/docs/guardrails/overview.md, website/docs/workflows/suspend-resume.md, accepted Index, original Issue 1177, original PRs 870/1390/821/1549 and their current statuses and PR1390 code diff
- Evaluation object: Additional autonomous organizational S3/S5 policy/authorization controller for per-agent local/provider/MCP tool rights beyond existing MCP checks, owner-provided local guards and pending native toolGuard
- Existing-work overlap: SHIPPED MCP can with discovery/execution enforcement; local/provider toolGuard is open unmerged PR 1390; alternative application-supplied wrappers and step filtering; separate S3 shared-commitment proposal in supervisor-commitment-control-20261119 is not this case
- Our on-top contribution: No qualified independent C construction for access policy; choose application-owned permission rules and source-native guard/hook improvement, not a second organizational policy controller
- Incremental benefit: No additional lawful decision/feedback loop, operating outcome or cost saving proven against current MCP and nearest original-native alternative; NOT_MEASURED
- Decision scope: Scoped NO_GO for the additional autonomous C authorization controller only; Issue 1177 and PR 1390 stay distinct native open work, and separate S3 GO / NEEDS_EVIDENCE remains intact
- Target transition: NO_QUALIFIED_C_TARGET
- Priority rationale: Authorization checks are enforcement of application-supplied policy, not demonstrated S3 current-portfolio management, complementary S3* correction or S5 purpose/policy resolution; S1/S2 mechanisms already exist and S4 has no relevant prospective environment task
- P1 dependencies: Original maintainers review PR 1390 and Issue 1177, test local/provider/MCP deny consistency, agent-child non-escalation, audit hooks and fail-closed controls against supported native policies
- P2 optional: Independently investigate a genuinely missing review or organization-level decision only after a user supplies concrete demand and lawful decisive authority; avoid duplicating the separate S3 case
- Proposed C construction: REJECTED — hypothetical cross-agent tool-policy chooser would need a separately composed S3 or S5 actor with legitimate independent options, enforceable first-party decision and later task feedback; no source-backed task or parent delegation currently qualifies it
- C sufficiency falsifier: Reproduce an original native case where current app-supplied policy, MCP can, existing hooks and PR 1390 cannot reach the required allowed/denied outcome, but a separately authorized developer-composed decisive actor can change it lawfully, return corrective feedback and outperform the cheapest alternative on the same workload
- Scenario basis: OBSERVED
- Proposal-stage decision: NO_GO
- Research disposition: NO_USEFUL_CHANGE
- Proposed validation: A native comparison of read-only and privileged subagents, MCP discovery and runtime denial, local/provider toolGuard pending implementation, scoped delegated roles, audit error/end, denied attempts, mismatched identity, stale authorizations and permitted controls; all NOT_RUN in this review
- Validation state: NOT_RUN
- Proposal falsifier: Demonstrate a repeatable owner-approved org-level policy decision and return not obtainable through the source-native per-tool checks with lower implementation and maintenance cost
- S1 disposition: Autonomous Agent executes tools; denial is a configured operational boundary, no extra C
- S2 disposition: Optional SubAgentManager coordinates otherwise independent specialists with developer configuration; already C at accepted historical ref, not policy S3
- S3 disposition: A per-agent guard has no separate current-portfolio task/capacity/commitment arbitration; separate supervisor S3 hypothesis is tracked elsewhere and remains proposal-only
- S3* disposition: onToolError/onToolEnd and trace hooks log or observe execution, not an independent protected review able to veto and correct a distinct organizational commitment
- S4 disposition: No verified environmental-future signal/options/feedback loop in the tool-access request; no justified construction
- S5 disposition: Application/operator authors retain rightful identity, roles and ultimate policy; tool guards enforce rather than legitimately establish/change that policy
- Result: NO_USEFUL_CHANGE
- External issue: DRAFT — NOT PUBLISHED
- Public fork Issue: DRAFT — NOT PUBLISHED
- Cost status: NOT_MEASURED

## Identity and pins

Accepted historical assessment at https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/assessments/vo/voltagent.md is included, repo/harness_id/review_ref match current catalog at c2e43bf4750841277b3e58d8ba80314121734764; original review ref resolves. Original default main is pinned at [e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c](https://github.com/VoltAgent/voltagent/commit/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c), unchanged from the historical case's original HEAD; this does NOT update accepted assessment grades or timestamp. Original https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/LICENCE (MIT) and https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/community/contributing.md examined. Public original feature discussion requires issue-first coordination. Fork state read at opensiro/meta: ACTIVE / ALLOW, so internal metadata can be written. External publication and personal CLA/DCO attestations are NOT authorized/inferred.

## Rights and authority

Application author supplies role/identity/rights; original maintainer retains code acceptance and architecture decisions. No autonomous agent may self-grant privileged tools or bypass parent S5. Third-party original Issues/PRs/comments, public fork issues and external PRs require exact separate consent; none is published or altered. Read-only source analysis is not a product implementation. The existing S3 proposal case is not merged and cannot be credited as shipped S3.

## Existing work / overlap

- SHIPPED native: [MCP authorization](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/mcp/authorization.md) documents developer-provided `authorization.can`, `filterOnDiscovery` and `checkOnExecution`; original [#870](https://github.com/VoltAgent/voltagent/pull/870) merged.
- REQUEST: original [#1177](https://github.com/VoltAgent/voltagent/issues/1177) is OPEN, asks per-agent permission, delegated read-only roles, audit denials. Several comments suggest step filtering and tool wrappers, not maintainer authorization to create an independent controller.
- PENDING native: original [#1390](https://github.com/VoltAgent/voltagent/pull/1390) OPEN, unmerged head `0fb458490703f5a89f6bb0e196c0c4f79bf95cb1`; inspected actual Agent types/code diff for `toolGuard` and deny `ToolDeniedError`, `onToolError`/`onToolEnd`. Proposed behavior is NOT shipped; PR-declared test plan is not a test executed here.
- Other adjacent: [#821](https://github.com/VoltAgent/voltagent/pull/821) OPEN traffic/concurrency management, [#1549](https://github.com/VoltAgent/voltagent/pull/1549) OPEN retry/tool replay repair, neither grants ultimate permission or proves an independent new audit actor.
- Existing first-party [SubAgentManager](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/packages/core/src/agent/subagent/index.ts), [hooks](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/hooks.md), [guardrails](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/guardrails/overview.md), [workflow suspend/resume](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/workflows/suspend-resume.md) provide delegation, observation and owner-supplied approval continuation, not automatic S5 delegation.

## Function ownership

| Function | Historical state | Current first-party evidence / decisive owner | Added C disposition |
| --- | --- | --- | --- |
| S1 | A | Agent task/tool loop with external tool feedback | Already A |
| S2 | C | Developer-composed subagent supervisor mediates specialist execution | Already C |
| S3 | — | No shown separate whole-team current commitment owner from tool permission filtering | Do not confuse with separate S3 GO proposal |
| S3* | — | Hooks capture error/end and metrics; no independent corrective reviewer | NOT_QUALIFIED |
| S4 | — | Tool permissions are per-call present conditions, no prospective environment adaptation | NOT_QUALIFIED |
| S5 | — | Human/application-authored policy is parent authority, not autonomous framework purpose choice | NO_TARGET |

Intentional omissions are UNVERIFIED beyond actual parent-controlled permission ownership. Historical labels are not current re-assessments or quality rankings.

## Capability priority

P0 NO_QUALIFIED_C_TARGET / NO_GO; research NO_USEFUL_CHANGE. P1 user/maintainer-led original #1177 / pending #1390 local permission and audit path, with narrow native regressions. P2 no autonomous C architecture recommendation. Falsifier as defined above. Confidence HIGH on native overlap, MODERATE on additional C usefulness without native tests or owner demand.

## Parallel contribution-on-top review

| Track | Native coverage → minimum on-top work | Distinct outcome versus cheapest alternative | Falsifier |
| --- | --- | --- | --- |
| A1 reuse | SHIPPED MCP `can`, registration-time filtering, execution-time checks; app can wrap local tools | Same authorized/denied user action with zero new OpenSiro C function | Demonstrate testable unsupported local/provider/child path after owner config |
| A2 native PR | OPEN #1390 provides Agent `toolGuard` and error/end hook receipt; evaluate before any implementation | Native contract directly targets issue #1177, without VSM-specific policy actor | Real unmet requirement outside its design once merged and tested |
| B1 integrate | Build tests/adapter around #1390 under original maintainer review, strict agent/child identity and denial logs | Potential original-native S1 security correctness, NOT a new S3/S5 C | Native guard already passes same outcomes |
| B2 independently composed policy actor | Additional cross-agent autonomous policy/portfolio controller with external authority and later decision feedback | No source-grounded legitimate actor/task or incremental benefit; reject now | Affected operator documents independent lawful choice, parent-controlled enforcement and matched outcome |
| B3 separate S3 case | Another current-commitment manager is separately recorded as GO/NEEDS_EVIDENCE | Distinct from per-tool permission and must not be double-counted | Existing traffic/supervisor/host queue subsumes it |

## Implementation options

Reuse shipped native MCP rules; follow native #1390 for local/provider policy without duplicating an open PR; preserve human role/approval rights. No new code is approved. Proposed positive/negative native tests NOT_RUN; costs NOT_MEASURED.

## Specification and domain alternatives

A policy DSL, static allowlist, `prepareStep` hiding, tool wrapper or authorization middleware can be valuable *native implementation choices* but is not automatically a VSM S3/S5 actor. S3* would require a distinct reviewer with separate evidence, decisive authorized hold/correction and later-work feedback; no qualifying use case verified. Do not infer S5 from access enforcement.

## Cost experiment

Matched native-vs-on-top effort, latency, protection and maintenance not measured. Require identical task/tool calls, identity contexts, denied audit records, and startup/operational costs, including negative stale/missing-policy and privilege-escalation cases, before any claim of value.

## Delivery and publication

- Review status: SOURCE_RECHECKED / PROPOSAL_ONLY; native runtime tests NOT_RUN; research NO_USEFUL_CHANGE.
- Case previous terminal decision: NO_GO at historical metadata revision [original case receipt](https://github.com/opensiro-contributions/voltagent/blob/bd2d99bbaef190f420697b546829e0ca0ed2d09e/.opensiro/issues/tool-authorization-native-overlap-20261119/roadmap.md); the original evaluated object is preserved and remains NO_GO. This source-first repeat is **non-blind** because the historical case was consulted during intake. It must NOT be counted as an independently isolated fresh-chat run.
- Separate case: [supervisor-commitment-control-20261119](https://github.com/opensiro-contributions/voltagent/blob/opensiro/meta/.opensiro/issues/supervisor-commitment-control-20261119/roadmap.md) is GO / NEEDS_EVIDENCE for optional S3 and not modified by this decision.
- If the canonical case is persisted, source links and exact commit readback are required. This record is not a public external Issue/PR, code patch, Index grade or verified native test.

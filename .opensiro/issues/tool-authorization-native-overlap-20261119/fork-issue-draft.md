# Fork Issue draft (VoltAgent; internal only)

**Destination:** opensiro-contributions/voltagent GitHub Issues, only after exact current-conversation approval.
**Proposed title:** Plan-only: bounded pre-dispatch delegation decision after child tool denial
**Status:** DRAFT — NOT PUBLISHED (do not send without owner's exact approval of title, destination and full text)

## Proposed body

A VoltAgent `Supervisor` with registered read-only `Researcher` and owner-authorized `Writer` subagents can observe a denied MCP write through the shipped `authorization.can` mechanism. A source-native proposal worth testing is an opt-in typed `SupervisorConfig` callback inside `SubAgentManager.createDelegateTool` **after resolving `targetAgents`, before parallel `handoffToMultiple`**. An app-composed current-team controller would choose `allow`, `hold`, `subset of selected registered agents`, or `escalate to owner`, without expanding any child's grants. Existing tool/handoff hooks could return feedback to the next delegation decision.

Before adding a port, test whether shipped supervisor `onToolStart` (which runs on the injected `delegate_task`) combined with child `onToolError`, `onHandoffComplete`, and MCP `can` already implements the same safe team decision and feedback. If yes, **do not** add a new controller. We have not independently reproduced reliable child MCP-denial attribution or the proposed effect. Related original [Issue #1177](https://github.com/VoltAgent/voltagent/issues/1177) and **unmerged** [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390) concern agent-local tool guards, not ultimate policy decisions; separate S3 budgets/commitment work must not be duplicated.

OpenSiro's accepted [historical Index assessment](https://github.com/opensiro/vsm-harness-index/blob/8f436270813b844aafc16917d69bc09661ef1544/assessments/vo/voltagent.md) (reviewed 2026-09-19; review_ref `44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de`, Profile 0.2.3 / Methodology 0.3.5) records `S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—`. S1 is the operating Agent loop; S2 is composed subagent coordination; S3 current team regulation is this **hypothetical** candidate; S3* independent audit, S4 future environment and S5 policy/identity were not credited in that historical review. These are ownership observations, not product quality scores or current grades. A means autonomous, C developer-composable, — not evidenced.

**Result:** proposal-stage `GO / NEEDS_EVIDENCE` is a conditional architectural hypothesis only, PLAN_ONLY; no native tests (NOT_RUN), measured benefit (NOT_MEASURED), maintainer preference or Index grade change. Adoption belongs to VoltAgent maintainers.

**Fork-local canonical evidence:** [roadmap](https://github.com/opensiro-contributions/voltagent/blob/opensiro/meta/.opensiro/issues/tool-authorization-native-overlap-20261119/roadmap.md), [Human](https://github.com/opensiro-contributions/voltagent/blob/opensiro/meta/.opensiro/issues/tool-authorization-native-overlap-20261119/issue.md), [AI](https://github.com/opensiro-contributions/voltagent/blob/opensiro/meta/.opensiro/issues/tool-authorization-native-overlap-20261119/constructor-sufficiency.md). AI-assisted analysis; no human review, first-party tests or maintainer consent asserted.

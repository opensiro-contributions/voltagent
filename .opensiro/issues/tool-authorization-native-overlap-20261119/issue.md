# VoltAgent — native tool-authorization overlap (2026-11-20 repeated review)

**Level 1 / Human.** The selected historical `NO_GO` was source-rechecked against the original; this is a **non-blind repeat**, not a new independent fresh-chat result.

**Target transition:** `NO_QUALIFIED_C_TARGET`
**Proposal-stage decision:** `NO_GO`
**Research disposition:** `NO_USEFUL_CHANGE`

[roadmap.md](roadmap.md) · [constructor-sufficiency.md](constructor-sufficiency.md) · [original #1177](https://github.com/VoltAgent/voltagent/issues/1177) · [toolGuard PR #1390](https://github.com/VoltAgent/voltagent/pull/1390)

## Decision

**NO_GO for a *new autonomous VSM C tool-authorization controller*, not NO_GO for fixing native per-agent permissions.** The accepted [Index assessment](https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/assessments/vo/voltagent.md) is dated; no historical regrade. Original source [main@e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c](https://github.com/VoltAgent/voltagent/commit/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c) remained unchanged from the earlier tool-authorization record. Fork is ACTIVE/ALLOW for internal metadata. No original maintainer message or public fork Issue is authorized or made.

The real user request #1177 is to distinguish authorized tools by agent identity and record denied calls. Native MCP `authorization.can` already enforces discovery/execution access. Agent-local/provider support is being proposed in the **OPEN, unmerged** PR #1390, with `toolGuard` and error/end hooks. Running a second organizational controller without an independently owned decision and corrective return would duplicate rather than solve a proven new issue.

## Six-function source census

| Function | Accepted historical state | Current observed closure / limitation | Roadmap verdict |
| --- | --- | --- | --- |
| **S1 · Operations** | A | First-party Agent executes model/tool actions | Existing |
| **S2 · Coordination** | C | Optional configured SubAgentManager coordinates specialist agents | Existing |
| **S3 · Current management** | — | Permission filtering is not a whole-team task/commitment decision; separate S3 proposal exists | No tool-auth C |
| **S3* · Complementary audit** | — | Tool hooks produce observations but no independent corrective reviewer | Not justified |
| **S4 · Future adaptation** | — | A current authorization check does not evaluate future environment and adjust later work | Not justified |
| **S5 · Policy/identity** | — | Operator/application supplies ultimate role and grant policy | Parent-reserved |

The historical vector is **S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—** from Profile 0.2.3 / Methodology 0.3.5, reviewed 2026-09-19, `review_ref=44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de`. Missing grades alone are not deficits.

## Native A vs on-top B

| Alternative | Status / evidence | Incremental user outcome |
| --- | --- | --- |
| Reuse MCP `can` + local tool wrapping | SHIPPED [MCP authorization](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/mcp/authorization.md), configured in application | Enforces scoped rights without new organizational decision |
| Integrate/finish #1390 | OPEN PR; actual diff covers Agent `toolGuard`, denied results and audit hooks | Directly closes requested native local/provider guard, subject to tests/review |
| Add independent S3/S5 policy controller | HYPOTHETICAL actor lacks validated parent delegation, independent lawful choice and later-work feedback | Not established; reject new C now |
| Separate S3 manager | Independently tracked [supervisor commitment case](https://github.com/opensiro-contributions/voltagent/blob/opensiro/meta/.opensiro/issues/supervisor-commitment-control-20261119/roadmap.md) GO/NEEDS_EVIDENCE | Different task; must not relabel authorization case |

**P0:** NO_QUALIFIED_C_TARGET / NO_GO. **P1:** finish/verify original issue #1177 and PR #1390 as source-native work if owner elects; test denial across MCP/local/provider tools, delegated child non-escalation, call audit, stale permissions. **P2:** no new controller proposed.

**Falsifier:** show a real application-owner task that native checks, pending guard and wrappers cannot meet, where a separately authorized independent C actor makes a different lawful decision, enforces it and receives later operational feedback at lower matched cost.

**Test status:** NOT_RUN. **Benefit/cost:** NOT_MEASURED. **External publication:** NONE. Historical NO_GO retained as prior result; new evaluation does not overwrite the separate S3 GO proposal.

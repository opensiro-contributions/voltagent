# VoltAgent — native tool-authorization overlap roadmap (OpenSiro plan-only)

**OpenSiro PLAN_ONLY · Final decision: NO_GO · Research outcome: NEEDS_EVIDENCE · 2026-11-19**

OpenSiro investigates whether source-native, VSM-informed organizational specifications can reduce the engineering and maintenance cost of agent harnesses. This is an *unmeasured hypothesis*, not a request for VoltAgent to adopt VSM or a claim that the project is missing six components.

**Accepted historical Index evidence:** [VoltAgent assessment](https://github.com/opensiro/vsm-harness-index/blob/34e11ec4dd52e1ba3ee0111d8bca73f13918f54f/assessments/vo/voltagent.md), reviewed 2026-09-19 against [44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de](https://github.com/VoltAgent/voltagent/commit/44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de); **S1=A, S2=C, S3=—, S3*=—, S4=—, S5=—**. These are historical ownership findings, not today's grades. The source reviewed here is [current main e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/README.md).

## User need and original-native overlap

[Issue #1177](https://github.com/VoltAgent/voltagent/issues/1177) requests per-agent tool access restrictions, denied-call visibility, and delegation boundaries. The original already ships MCP authorization with discovery filtering and execution checks, as documented [here](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/mcp/authorization.md), following merged [PR #870](https://github.com/VoltAgent/voltagent/pull/870). [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390) is **open, not merged**; it proposes the remaining agent-level \`toolGuard\`, including denial and error/end hooks. An open PR is not shipped functionality or independent proof that tests passed.

## Decision and next steps

**NO_GO now:** do not build a separate VSM S3/S5 controller, duplicate \`toolGuard\`, or open a new maintainer feature Issue. The permission guard is enforcement of application-supplied authority, not evidence of an agent-owned whole-system S3 or ultimate-policy S5 decision.

**P0:** proposed additional VSM controller — **not qualified / rejected now**. **P1:** assess the existing original PR #1390 and compare MCP \`can\` vs agent-level guard with source-native allow/deny, delegation and audit tests *if independently authorized*. **P2:** none.

Reopen only on evidence of a materially different user outcome that the original solutions cannot supply, with a real autonomous decision owner, enforceable state and downstream feedback. No native tests were run for this roadmap, cost reduction is **NOT_MEASURED**, and OpenSiro claims no implementation or maintainer endorsement.

**OpenSiro case:** [Human decision](https://github.com/opensiro-contributions/voltagent/blob/opensiro/meta/.opensiro/issues/tool-authorization-native-overlap-20261119/issue.md) · [AI/developer sufficiency contract](https://github.com/opensiro-contributions/voltagent/blob/opensiro/meta/.opensiro/issues/tool-authorization-native-overlap-20261119/constructor-sufficiency.md) · [receipt](https://github.com/opensiro-contributions/voltagent/blob/opensiro/meta/.opensiro/issues/tool-authorization-native-overlap-20261119/roadmap.md).

**AI disclosure:** prepared with AI assistance; no independent human review, verified savings, native test execution, or external maintainer approval is claimed.

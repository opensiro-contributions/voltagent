# VoltAgent — native tool-authorization overlap roadmap

**OpenSiro PLAN_ONLY · NEEDS_EVIDENCE (terminal research disposition) · final operator decision: NO_GO · Public fork Issue NOT PUBLISHED**

**Level 1 — Human decision.** [Complete AI/developer sufficiency contract](constructor-sufficiency.md) · [source-pinned receipt](roadmap.md) · [unpublished fork Issue draft](fork-issue-draft.md).

## 1. Why OpenSiro and accepted historical assessment

OpenSiro tests whether reusable organizational specifications informed by the Viable System Model (VSM), integrated into the simplest source-native solutions, can standardize agent-harness development and reduce implementation, integration and maintenance cost. This is an unmeasured hypothesis; VoltAgent's maintainers need not adopt VSM and no savings are claimed.

**STARTING POINT — ACCEPTED INDEX, NOT THE TARGET: S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—.**

[Accepted VoltAgent assessment](https://github.com/opensiro/vsm-harness-index/blob/34e11ec4dd52e1ba3ee0111d8bca73f13918f54f/assessments/vo/voltagent.md) at Index commit [34e11ec4dd52e1ba3ee0111d8bca73f13918f54f](https://github.com/opensiro/vsm-harness-index/commit/34e11ec4dd52e1ba3ee0111d8bca73f13918f54f); assessment blob \`c7dec10ee48c461833c33e0ceb408cd49ed57fdd\`; reviewed 2026-09-19 at original [review_ref 44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de](https://github.com/VoltAgent/voltagent/commit/44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de); Profile **0.2.3** / Methodology **0.3.5**. It is a dated ownership classification, not a current default-branch grade.

| VSM function | Historical accepted state | What the evidence means here |
| --- | --- | --- |
| S1 · Operations | **A** | Autonomous tool-using Agent operational loop; no mandatory constructor |
| S2 · Coordination | **C** | First-party composable multi-agent coordination; preserve current semantics |
| S3 · Current whole-system control | **—** | No accepted decisive whole-system control path at the historical ref; current per-tool permissions are not automatically S3 |
| S3* · Complementary audit | **—** | Execution/logging hooks are not by themselves independent complementary audit |
| S4 · Prospective adaptation | **—** | Nothing in this tool-authorization use case independently supports an external/future adaptation actor |
| S5 · Ultimate policy/identity | **—** | Application-supplied role checks are enforcement, not autonomous ultimate policy ownership |

**Pins and boundary:** original [\`main\` e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c](https://github.com/VoltAgent/voltagent/commit/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c), observed 2026-11-19; runtime boundary is first-party \`@voltagent/core\` Agent/supervisors, native MCP permissions and surrounding workflow hooks. Excludes external MCP servers, business policies installed by application developers, separately operated VoltOps and the maintainers' governance. Correct fork: [opensiro-contributions/voltagent](https://github.com/opensiro-contributions/voltagent). Initial metadata branch owner control \`PAUSE\` / attention \`DORMANT\`. GitHub root license is MIT; external-contributor formalities, personal attestations and specific AI requirements require verification before any external PR. Assessment was reviewed **61 days** before observation; an Index-owned pinned reassessment is recommended **before relying on grades for new architecture**, but is not a roadmap stop.

\`A\`, \`C\` and \`P\` describe different decision ownership arrangements, not maturity. A historical \`—\` is not a request to fill the missing score.

## 2. User capability and immediate decision

**Observed user problem:** author of [original Issue #1177](https://github.com/VoltAgent/voltagent/issues/1177) seeks agent-specific access rights to tools, including narrower delegated worker rights and auditable denials. Example counterfactual: a read-only research agent must not execute a destructive tool while a different legitimate agent can.

**Native alternative on current original source:** MCP \`authorization.can\`, \`filterOnDiscovery\` and \`checkOnExecution\` already documented on [main](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/mcp/authorization.md); merged [PR #870](https://github.com/VoltAgent/voltagent/pull/870) supplies this functionality. For local/provider agent tools, [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390) is an **OPEN_PR** proposing Agent \`toolGuard\`, denial and hooks. PR code is not shipped main.

**Final operator decision: NO_GO** for a new independent VSM controller or duplicate tool-authorization implementation. Existing native mechanisms and a close open PR provide the least-overlapping route. A distinct valuable *S3 or S5 organizational decision* beyond access checking has not been established. This is **NEEDS_EVIDENCE** for a new constructor, not proof that Issue #1177 is already fully solved.

## 3. Original-native overlap versus residual work

| Scope | Native status | Materially distinct gap for a new OpenSiro constructor |
| --- | --- | --- |
| MCP access and discovery | **SHIPPED**: first-party [MCP Authorization docs](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/mcp/authorization.md), [merged #870](https://github.com/VoltAgent/voltagent/pull/870) | None shown for equivalent MCP tool restriction |
| Agent-local/provider tool restrictions and audit | **ISSUE_ONLY + OPEN_PR**: [#1177](https://github.com/VoltAgent/voltagent/issues/1177), [#1390](https://github.com/VoltAgent/voltagent/pull/1390) | Review/integrate existing PR first; no proven different first-party interface needed |
| Model retry replay of tool side effects | **ISSUE_ONLY + OPEN_PR**: [#1537](https://github.com/VoltAgent/voltagent/issues/1537) / [#1549](https://github.com/VoltAgent/voltagent/pull/1549) | Distinct repair, not a basis for constructing S3 or S5 |
| Whole-system current priorities / ultimate policy | **UNVERIFIED** today; historical Index **—** | No source-native user task demonstrates autonomous ownership, alternatives and closure |

No code or native tests were executed in this plan-only study. The status of open PRs was checked on 2026-11-19, not inferred from titles.

## 4. Priority and conditional sufficiency

| Priority | Candidate | Decision |
| --- | --- | --- |
| **P0 — proposed S3/S5 controller** | A developer-defined autonomous decision actor with real whole-application choice, authorized effect and later feedback | **REJECTED NOW**: no unique real operator task beyond tool access; a permissions guard does not qualify as S3/S5 |
| **P1 — original-native reuse** | Read original PR #1390 against shipped MCP \`can\`; validate differentiated agent roles, delegated denial, audit signals, and compatibility if implementation/review is separately authorized | **Conditional research**, not a change commitment |
| **P2 — optional other function** | None | **NONE**; no invented extra VSM capability |

A real new \`C\` constructor would need a material organizational disturbance, multiple legitimate decisions including \`hold\`, an independently composed authorized decision-maker, first-party enforcement and feedback in a later operational episode. The existing tool-auth use case has **policy enforcement**, not an established first-party developer-composed whole-system autonomous management decision. **Sufficiency verdict: NOT QUALIFIED**.

## 5. Falsifiable acceptance and stop gates

- **Native positive:** a research agent may call \`searchDocs\` but cannot execute \`deleteNote\`; an authorized admin can. Verify denial occurs before side effects, both for MCP and eligible local/provider tools according to the exact implementation.
- **Delegation / negative:** a delegated worker cannot acquire broader rights than its authorized principal; a denied action never executes, and a human/parent-reserved decision cannot be bypassed.
- **Return / audit:** error/end hook or policy receipt accurately identifies the denied attempt and whether tool execution occurred. Logging is not itself S3* or S5.
- **Comparison:** run the same user story on current main and pending PR #1390 (pinned head), distinguish already-shipped MCP case from PR-only local case.
- **Stop:** if existing source-native tools and PR satisfy the user task with less work, avoid new interface; if no real organizational decision actor and feedback, do not label it \`S3=C\`/\`S5=C\`.

These are **proposed tests, NOT EXECUTED** in this roadmap.

## 6. Independent paths and cost

Original-native: re-evaluate/possibly contribute to [existing #1390](https://github.com/VoltAgent/voltagent/pull/1390) rather than duplicate. This requires fresh Upgrade intent, contributor policy, tests and each exact publication approval. Methodology: only change Profile/Skills for independently evidenced semantic ambiguities; no such ambiguity established. Optional licensed domain fork could be considered for independently proven novel requirements but is not admitted here.

**Cost status: NOT_MEASURED.** Comparing future development/review/tests/maintenance against shipped MCP capability and existing PR would be required before claiming savings.

## 7. Decision and handoff

**Result: NEEDS_EVIDENCE; FINAL OPERATOR DECISION: NO_GO.** **Do not** construct a speculative new VSM controller, duplicate toolGuard or publish a new original maintainer issue. **Do** retain the source-native links; if separately requested and authorized, inspect original PR #1390 for a precise residual gap. To reverse the decision, a different real operator outcome plus source-native proof of a complete authorized organizational decision and later feedback must be supplied.

The [AI companion](constructor-sufficiency.md) records function-specific falsification and baseline; [receipt](roadmap.md) repeats this decision. Fork-local case files are not a public GitHub Issue. [Public fork Issue draft](fork-issue-draft.md) is **NOT PUBLISHED** until exact current-conversation owner consent; no original Issue/comment/PR is authorized. No code, Index grade change, independent human review or native-test pass claimed.

**AI involvement disclosure:** AI-assisted analysis and drafting; no independently executed tests, guaranteed correctness, maintainer endorsement or cost advantage.

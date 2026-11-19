# VoltAgent — AI/developer sufficiency contract, native-first

**Level 2 · PLAN_ONLY / NEEDS_EVIDENCE · FINAL OPERATOR DECISION: NO_GO · NOT PUBLISHED as GitHub Issue**

[Human Issue decision](issue.md) ↔ [Receipt](roadmap.md) · [original issue](https://github.com/VoltAgent/voltagent/issues/1177) · [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390)

## 1. Functional boundary and accepted provenance

**Historical accepted Index vector (same as Human): S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—**. [Accepted assessment](https://github.com/opensiro/vsm-harness-index/blob/34e11ec4dd52e1ba3ee0111d8bca73f13918f54f/assessments/vo/voltagent.md), file blob \`c7dec10ee48c461833c33e0ceb408cd49ed57fdd\`, \`review_ref=44b4c8e4998ce56095b2f0e4eaf1a988f5e6d0de\`, \`reviewed_at=2026-09-19\`, Profile 0.2.3 / Methodology 0.3.5. Current original [HEAD e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c](https://github.com/VoltAgent/voltagent/commit/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c), observed 2026-11-19. Old 61-day review merits **advisory** Index reassessment if an architectural grade is needed, but a current roadmap must use current code and issue evidence.

System in focus: first-party VoltAgent single application and \`@voltagent/core\` agent/tool execution, delegated agents, native MCP authorization and associated hooks; not external MCP servers/LLM providers, business policy engines, VoltOps service, or maintainers' policy authority.

**Function distinctions:** S2 manages interference among operational peers; S3 would decide among current whole-system resource/priority/commitment options and receive operational feedback; S3* requires independent complementary examination; S4 interprets external futures and drives authorized adaptation; S5 legitimately resolves purpose and ultimate policy. A boolean tool guard and trace hooks alone establish none of S3/S3*/S4/S5.

## 2. Current original source and competing implementation

| Mechanism | Current evidence, status | Decision-owner and return consequence |
| --- | --- | --- |
| MCP permission configuration | **SHIPPED** [\`website/docs/agents/mcp/authorization.md\`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/website/docs/agents/mcp/authorization.md), [merged #870](https://github.com/VoltAgent/voltagent/pull/870) | Application-defined \`MCPConfiguration.authorization.can\` chooses allow/deny on discovery or execution; returns error/decision, does not delegate ultimate policy to a framework controller |
| Agent-level \`toolGuard\` | **OPEN_PR only** [#1390](https://github.com/VoltAgent/voltagent/pull/1390), observed head \`0fb458490703f5a89f6bb0e196c0c4f79bf95cb1\`; proposed \`packages/core/src/agent/agent.ts\`, hooks and tests | Author-provided hook blocks tool execution, relays denial through error/end hooks; test code in PR diff is not a passing run or shipped main |
| Per-agent rights request | **ISSUE_ONLY** [#1177](https://github.com/VoltAgent/voltagent/issues/1177) open | Real request for role-scoped tools and denied-call audit; no demonstrated separate autonomous S3 or S5 decision task |
| Tool retry side-effect replay | **OPEN_PR** [#1549](https://github.com/VoltAgent/voltagent/pull/1549) for open [#1537](https://github.com/VoltAgent/voltagent/issues/1537) | Related reliability repair with side-effect impact, not an additional organizational controller |

Source-native \(current main → competing work → residual\): main already supports MCP \`can\`; PR #1390 proposes local/provider guard; any residual cross-agent right inheritance or trustworthy enforcement must be checked against actual PR semantics and tests, not inferred from request wording alone. A pending PR does not make the gap shipped. **Overlap receipt: PARTIAL_OVERLAP**.

## 3. Counterfactual and rejected constructor

Authentic user request: restrict different agents in one system to their permitted tools. For an S3-style new \`C\` claim, the missing new task would have to be a *material* whole-system current decision (e.g., selecting among competing resource/commitment policies after a real disturbance), not applying an author-supplied access list. For S5 it would need rightful overall policy/identity arbitration, not a static access check.

A proposed five-link construction **is not qualified**:
| Necessary logical link | This repository's presently evidenced route | Residual |
| --- | --- | --- |
| A · real source/trigger | Agent requests tool call with context/arguments; MCP API already receives discovery/execution event | This is tool invocation, **not evidence of whole-system S3 tension** |
| B · real alternatives and state | Allowed or denied permission under supplied rules | No proved organizational alternatives, priorities, versioned commitment state or \`hold\` decision |
| C · developer-composed autonomous decisive owner | Application-defined \`can\` or PR \`toolGuard\` callback | Callback is application policy enforcement, not an independently developer-composed agent exercising S3/S5 discretionary rights |
| D · first-party enforced effect | SHIPPED MCP check / OPEN_PR agent check | Reuse. No new organizational action bridge demonstrated |
| E · later operational feedback | Permission denial, error/end hooks in proposed PR | No demonstrated later whole-system decision/feedback loop; error reporting alone is insufficient |

Removing a hypothetical autonomous policy agent leaves the developer's deterministic permission policy making the same allow/deny choice. Therefore these ports do **not** prove the proposed S3/S5 \`C\`. A new controller would be speculative duplication.

## 4. Priorities (identical to Human)

**P0 — REJECTED NOW:** standalone VSM S3/S5 autonomous controller or parallel local tool policy API; no independent material user delta.

**P1 — conditional native research only:** if a separate approved action is requested, review original PR #1390 at exact head, verify main vs open-PR per-agent role behavior for local and provider tools, MCP \`can\` behavior, denial timing/audit and a delegated worker's effective scope. Reconcile actual contributor, AI, CLA/DCO and PR checks before any external action.

**P2: NONE — no secondary constructor.**

**Functional-delta receipt: DELTA_PENDING / additional S3/S5 controller NOT QUALIFIED.** The original Issue documents a tool-auth need; it does not document a new independently valuable management/policy-owning agent. The selected operator decision remains **NO_GO**, not delayed approval.

## 5. Source-native acceptance / falsification (NOT EXECUTED)

| Scenario | Actor/trigger | Observable positive or negative outcome | Falsifier |
| --- | --- | --- | --- |
| V-A: existing MCP alternative | Reader role requests \`delete_item\` through MCP; admin role requests same tool | Reader does not see forbidden tool when discovery filtering enabled and cannot execute it when execution check enabled; admin legitimately executes | Request blocked only in display but executable, or role context ignored |
| V-B: PR-only local tool denial | Agent with \`toolGuard\` denies \`delete-note\` through Agent tool execution | Actual tool execute callback not called; denied result and error/end hooks report denial | Tool executes first; missing/false denial report |
| V-C: delegated right boundary | Supervisor delegates to restricted worker; worker attempts higher-privilege tool | Worker cannot gain permissions beyond explicit scope; attributable denial, no effect | Generic inherited role silently widens tool rights |
| V-D: native baseline and controller comparison | Same tool-control task against main MCP behavior and open PR head | Document genuine newly possible task, effort and native compatibility; a hypothetical extra VSM controller must demonstrate a materially different organizational choice/feedback | A new controller changes only API arrangement, not user outcome or ownership |

These test ideas are not source-native executions, and V-C behavior is not proven by PR #1390 merely because it supplies a guard. A later implementation would need real harness tests and rights/authority proofs. Do not label any future native test as passed without a real reproducible receipt.

## 6. Rights, exclusions, cost and final decision

MIT SPDX in GitHub original metadata, published [contributor guide](https://voltagent.dev/docs/community/contributing/), verified [fork opensiro-contributions/voltagent](https://github.com/opensiro-contributions/voltagent) parent identity, metadata initialized PAUSE/DORMANT. CLA/DCO, AI restrictions and required human attestations **not conclusively cleared**. Do not submit a third-party Issue/PR/comment without exact separate current-conversation publication approval, or a fork-local public Issue without its own exact approval.

Cost comparison would measure same user task, source-code effort, review/test burden, maintenance, and per-actor permission outcomes against existing MCP code and PR #1390; **NOT_MEASURED**. No Profile/Skills amendment suggested; optional experimental fork requires its own justification.

**Result: NEEDS_EVIDENCE · FINAL OPERATOR DECISION: NO_GO.** Do not implement a second controller or duplicate PR #1390. Reconsider only if an independently demonstrated operator need cannot be met by the existing native approach, and a complete function-specific autonomous decision/authority/operation/feedback witness is constructed. Existing PR review/maintenance may be separately proposed under normal permissions, not automatically admitted.

**AI assistance disclosed; no independent human audit, original-maintainer endorsement or executed source-native tests claimed.**

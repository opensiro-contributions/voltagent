# VoltAgent original Feature Request — owner-visible native-template comparison

**Status: PREPARED_FOR_EXACT_OWNER_REVIEW / NOT PUBLISHED.** Same existing canonical case `.opensiro/issues/tool-authorization-native-overlap-20261119/`; this document is a *review packet*, not a second Human Issue or a new independent proposal. Checked 2026-11-22T17:30:04Z.

## Intended GitHub action and immutable evidence

- **Action:** create a new, publicly visible Feature Request GitHub Issue in **`VoltAgent/voltagent`**, not in the fork, not a Discussion or a comment on #1166/#1177.
- **Original default HEAD checked:** [`e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c`](https://github.com/VoltAgent/voltagent/commit/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c).
- **Native first-party Feature Request form (immutable):** [`.github/ISSUE_TEMPLATE/feature_request.yml`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/.github/ISSUE_TEMPLATE/feature_request.yml), form git blob `dec965d75e055faf65fd96fffb9af20299c5456e`.
- **Live form link:** https://github.com/VoltAgent/voltagent/blob/main/.github/ISSUE_TEMPLATE/feature_request.yml
- **Native Issue settings:** [`.github/ISSUE_TEMPLATE/config.yml`](https://github.com/VoltAgent/voltagent/blob/e9fc599f6059afcd88b34f2bfc50d0d1d6a0877c/.github/ISSUE_TEMPLATE/config.yml), blob `51a926c7380f4e4edbeb920db9e6b0c5a4dd7bfd`; `blank_issues_enabled=true`, with separate Questions/Discussions contact link.
- **Same-case source:** [Human `issue.md`](issue.md) · [canonical `roadmap.md`](roadmap.md) · [exact original-facing body `original-issue-draft.md`](original-issue-draft.md).
- **Exact title:** `Proposal: scoped delegate_task hold or subset after a child denial — Opensiro VSM architecture review`.
- **Exact title SHA-256:** `0b10245f34f95d2a0750b027b85966cdad9ba5c3a1e89f2f10d11c611ea93404`.
- **Exact body SHA-256:** `d601450864fa0b0a03b7aedc4162d09eee70d52d2101629f3a55321c3ca0ab6c`.
- **Native form advisory:** `title: "[FEAT]"` is a suggested prefill, **not** a mandatory prefix. `labels: ["enhancement"]` is the template-suggested label, not a promised label on an API-created Issue. No checkboxes or dropdowns exist in this current form.

## Native field-by-field comparison — complete original template

| Native form field | Required? | Actual proposal | Fit / difference |
| --- | --- | --- | --- |
| `Is your feature request related to a problem? Please describe.` | YES | A matching `###` field in the first of seven original-facing sections, followed by current/source-specific problem and counterexample | POPULATED — native-required label appears verbatim |
| `Describe alternatives you've considered` | NO | `Closest existing project-native solution`, `Minimal proposed addition`, and native-wrapper comparator in the body | CONTENT PRESENT, but not separated under the optional exact native label; disclose, do not claim exact field label |
| `Additional context` | NO | Separate historical VSM assessment/provenance, source-locked architectural rationale, tests and disclosure | CONTENT PRESENT, not under the optional exact native label |
| `Describe the thing to improve` | YES | Matching `###` label in first section, followed by typed pre-handoff hold/selected-subset proposal | POPULATED — native-required label appears verbatim |

**Reviewable differences:** The proposal title begins with `Proposal:` rather than the form's optional `[FEAT]` prefill. Two optional fields are supplied semantically but not as named form fields. The seven OpenSiro external sections contain far more material than the native form's minimum. No *required* native field is missing. Whether to change advisory presentation is an editorial/maintainer-fit choice, not a reason to claim syntax noncompliance or falsify checkbox attestations.

## Source and duplicate review, bounded and dated

- Original [#1166](https://github.com/VoltAgent/voltagent/issues/1166): OPEN; pre-action/tool-call authorization, including community mention of `on_delegation`.
- Original [#1177](https://github.com/VoltAgent/voltagent/issues/1177): OPEN; per-tool authorization middleware and delegation-related permissions.
- Original [PR #1390](https://github.com/VoltAgent/voltagent/pull/1390): OPEN/unmerged; separate tool authorization guard, no shipped SubAgentManager pre-handoff subset port established.
- **Deduplication limit:** differences remain at *selection of permitted children before next parallel handoff* vs generic per-tool authorization. These do not establish first-party developer demand or guarantee maintainers want a separate Issue; maintainer may route response into #1166/#1177.
- **Original source functionality:** current first-party `createDelegateTool` resolves targets then dispatches via `handoffToMultiple`; current `onToolStart` does not return a typed subset selection. A native-only wrapper could falsify the need for this proposed API. No native tests executed.

## Checks and publication boundary

- Case structural and current Human/AI template validators: **PASS**.
- Exact seven-section external draft/provenance/canonical original-and-S3 transition: **PASS**.
- Original live channel, required native form fields, verified source SHA: **PASS**.
- Source-head, actual provider/template and existing original Issues/PRs must be checked **again immediately before any authorized POST**.
- **This document is NOT owner approval**, and a repository `owner_control=ALLOW` on internal metadata is not consent to post to `VoltAgent/voltagent`.
- The outward owner approval request must **also show the full exact public body in the conversation**, not merely link this preview/draft, per [Upstream publication rule](https://github.com/opensiro/upstream/blob/main/PROTOCOL.md#exact-public-github-issue-payload-gate--fork-and-original).
- **No external Issue, comment or PR was published.** Obtain separate current-conversation approval of exact target, action, final title and complete body; any change after preview triggers new checks and renewed consent.

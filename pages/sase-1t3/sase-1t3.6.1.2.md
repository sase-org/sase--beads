# Bead: sase-1t3.6.1.2 — Indexed named-agent and dismissed-bundle resolution

[Bead Pages](../README.md) / [sase-1t3.6.1](sase-1t3.6.1.md) / sase-1t3.6.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.6.md) · **Assignee:** `sase-1t3.6.1.2` · **Size:** medium
**Created:** 2026-11-16 08:12:23 EST
**Plan:** [202611/indexed\_agent\_lookups.md](https://github.com/sase-org/sase--plans/blob/main/202611/indexed_agent_lookups.md)

## Description

named-bundles: replace find_named_agent's full artifact scan and recursive dismissed-bundle scan with Rust-backed exact name/workflow queries; maintain the archive projection on writes and prove ranking and recovery parity.

## Notes

[2026-11-16T18:07:02Z · sase-1t3.6.1.2] PROPOSED FOLLOW-UP: just-check scoped failures reproduce on clean tree (test_agent_search_archive_cli_matches_shared_corpus_order, test_tui_list_order_matches_cli_identity_order, test_detached_failed_gate_pins_root_claim, corpus facade workflow_child/light_rows) — unrelated to named-bundles cutover

[2026-11-16T18:07:10Z · sase-1t3.6.1.2] PROPOSED FOLLOW-UP: fakey hijack/provider-drain e2e and launch-chain scoped failures in untouched areas — verify against session-clans phase (sase-1t3.6.1.3) and hijack epic

[2026-11-16T18:09:32Z · sase-1t3.6.1.2] CLOSE-BLOCKED: Code complete and verified (see verification note). Epic-symbol rows for sase-1t3.6.1.2 deleted locally and re-keyed to parent sase-1t3.6.1; symvision passes without 1.2 rows proving consumption. sase bead close refuses due to origin/master still carrying 1.2 rows, which only land can update. Land agent: landing this branch replaces upstream 1.2 rows with 1.6.1 rows; drop 1.6.1 rows on epic verification of consumption, then close this phase.

## Dependencies

- **Depends on:** [sase-1t3.6.1.1](sase-1t3.6.1.1.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.6.1.3](sase-1t3.6.1.3.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.6.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.6.1.2/README.md) | [sase-1t3.6.1.2](sase-1t3.6.1.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8593b14`](https://github.com/sase-org/sase-core/commit/8593b148fd3b00678e21775f414f19c0a99104e4) | feat(agent-archive): project workflow\_name column with name-or-workflow lookup | [sase-1t3.6.1.2](sase-1t3.6.1.2.md) | 2026-11-16 13:14:41 EST |
| sase | [`e1d81ee`](https://github.com/sase-org/sase/commit/e1d81ee6c6f2adc9c99819764ed7fa8740443f63) | feat(agent-names): indexed lookup via lookup\_agent\_artifacts with workflow-name ranking | [sase-1t3.6.1.2](sase-1t3.6.1.2.md) | 2026-11-16 13:15:57 EST |

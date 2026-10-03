# Bead: sase-1eu.8 — Remove the flag and finish docs, help, glossary, and release note

[Bead Pages](../README.md) / [sase-1eu](README.md) / sase-1eu.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ve](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ve.md) · **Assignee:** `sase-1eu.8` · **Size:** small
**Created:** 2026-10-02 11:34:02 EDT · **Closed:** 2026-10-02 22:18:48 EDT
**Plan:** [202610/three\_pane\_splits.md](https://github.com/sase-org/sase--plans/blob/main/202610/three_pane_splits.md)

## Description

unflag-docs: delete the three_pane_splits Off branch and close its flag bead, then clear leftover epic-symbol entries. Finish docs/ace.md, docs/pager.md, configuration docs and help sheets, update the Deck Panel glossary strand, and write the changelog-facing commit message.

## Notes

[2026-10-03T02:18:08Z · sase-1eu.8--1] PROPOSED FOLLOW-UP: test_prompt_key_io_probe_counts_main_thread_calls fails on clean base too (FileNotFoundError vcs_xprompt_mru.json; repro with and without unflag-docs changes, tool run 3ccd10a67fb5e631bc89d0d57213f95a)

[2026-10-03T02:18:20Z · sase-1eu.8--1] PROPOSED FOLLOW-UP: test_empty_panel_semicolon_hops_to_palette_and_back parallel-lane timeout is tracked by task sase-1al (passes serially with and without unflag-docs changes; TimeoutError under load1~28 in run 3ccd10a67fb5e631bc89d0d57213f95a)

[2026-10-03T02:18:31Z · sase-1eu.8--1] PROPOSED FOLLOW-UP: test_tribe_and_tab_modal_shows_tab_input WaitForScreenTimeout under parallel check load only (passes serially with and without unflag-docs changes; no existing task bead found; run 3ccd10a67fb5e631bc89d0d57213f95a)

[2026-10-03T02:18:48Z · sase-1eu.8--1] unflag-docs verified: three_pane_splits flag fully removed (zero refs in src/tests/docs/glossary), docs/ace.md docs/pager.md docs/configuration.md and deck-panel glossary updated, Off-branch golden deleted; scoped check run 3ccd10a67fb5e631bc89d0d57213f95a shows no failures in touched files (98 deck/pager/pane-grid tests pass); 3 NEW failures dispositioned as out-of-scope (1 repros on clean base, 2 parallel-load flakes passing serially on both trees, one tracked by sase-1al) with PROPOSED FOLLOW-UP notes

## Dependencies

- **Depends on:** [sase-1eu.5](sase-1eu.5.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1eu.7](sase-1eu.7.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eu.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eu.8.md) | [sase-1eu.8](sase-1eu.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c62e4f1`](https://github.com/sase-org/sase/commit/c62e4f1491e571bc6ac62073f156c31687a88875) | feat(ace-pager): remove three\_pane\_splits flag and finish unflag docs (sase-1eu.8) | [sase-1eu.8](sase-1eu.8.md) | 2026-10-02 22:20:06 EDT |

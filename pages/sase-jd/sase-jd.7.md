# Bead: sase-jd.7 — PR badge and origin chip on Patch rows and detail

[Bead Pages](../README.md) / [sase-jd](README.md) / sase-jd.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xp](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xp/README.md) · **Assignee:** `sase-jd.7` · **Size:** medium
**Created:** 2026-08-10 19:15:00 EDT · **Closed:** 2026-08-10 21:18:37 EDT
**Plan:** [202608/external\_artifact\_ingestion.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_artifact_ingestion.md)

## Description

patch_pr_ui: render the PR badge and the origin chip as two independent signals on Patch rows and in the detail panel, add the origin query property, and add the mark-origin/adopt operation that clears unknown records.

## Notes

[2026-08-11T01:18:04Z · sase-jd.7] PROPOSED FOLLOW-UP: Regenerate stale snippet_save_confirm_diff_120x40.png golden — tests/ace/tui/visual/test_ace_png_snapshots_snippet_save.py::test_snippet_save_confirm_diff_png_snapshot fails on a clean checkout (verified via git stash) because the golden still shows the Stitches sub-tab label as "Commits"; sase-j8 (Commits to Stitches rename) has closed all phases but has not yet landed in this workspace baseline.

[2026-08-11T01:18:37Z · sase-jd.7] Implemented patch_pr_ui end to end: (1) origin chip (external/origin?, sase renders nothing) added alongside the existing PR badge in _patch_list_helpers.py (format_patch_option/calculate_entry_display_width/row_signature kept in sync) and an 'Adopted from an external PR' note in patch_detail.py + display.py for PR_ORIGIN=external; (2) origin: query property added to tokenizer.py/matchers.py/searchable.py AND mirrored in the Rust sase-core crate (types.rs VALID_PROPERTY_KEYS, tokenizer.rs, matchers.rs match_origin, evaluator.rs dispatch, searchable.rs) since sase patch query parsing is Rust-backed — discovered this only after parse_query() rejected origin: at runtime; golden corpus/parity tests updated on both sides (Python inline-snapshot golden tests + Rust query_evaluator_parity.rs), docs/query_language.md updated; (3) mark-origin/adopt operation: sase patch set-origin <name> <sase|external|unknown> CLI (parser_patch.py/patch_handler.py) plus a TUI action (action_mark_pr_origin bound to 'o' in the Patches tab via PrOriginModal), with update_patch_pr_origin_atomic added to status_state_machine/field_updates.py. Found and fixed a real 'o' keybinding collision with the existing cycle_grouping_mode action (Agents tab) via _app_action_availability.py tab-gating, caught by just test-visual. Verified: just check green (fmt/ruff/mypy/symvision/etc, scoped tests escalated to full suite and passed); just test-visual 651 passed/1 skipped, with the one remaining failure (test_snippet_save_confirm_diff_png_snapshot) confirmed pre-existing/unrelated via git stash (stale golden from the not-yet-landed sase-j8 Commits->Stitches rename, noted as a follow-up); cargo test -p sase_core and cargo clippy clean in the linked sase-core checkout; 61 new/updated focused Python tests passing across row rendering, detail panel, query matching, CLI, TUI action, and field-update persistence.

[2026-08-11T01:19:24Z · sase-jd.7] Verified: patch_pr_ui end-to-end (origin chip + PR badge rendering, origin: query property in Python and Rust sase-core, set-origin CLI/TUI action); just check and just test-visual green aside from pre-existing unrelated snapshot failure.

## Dependencies

- **Depends on:** [sase-jd.3](sase-jd.3.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jd.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jd.7/README.md) | [sase-jd.7](sase-jd.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c63b32b`](https://github.com/sase-org/sase/commit/c63b32b93c25cbbe9abc77ccf82c70b68788bb69) | feat(ace): render PR origin chip and add origin: query property | [sase-jd.7](sase-jd.7.md) | 2026-08-10 21:20:36 EDT |

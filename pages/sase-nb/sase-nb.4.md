# Bead: sase-nb.4 — The shared flag visual language

[Bead Pages](../README.md) / [sase-nb](README.md) / sase-nb.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03v.md) · **Assignee:** `sase-nb.4` · **Size:** small
**Created:** 2026-08-16 12:25:11 EDT · **Closed:** 2026-08-16 17:41:10 EDT
**Plan:** [202608/feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags.md)

## Description

look: register the flag bead type's glyph and accent, and add the shared bead_flag_presentation module that renders the flag key chip and the urgency-graded removal countdown for every surface.

## Notes

[2026-08-16T20:37:57Z · sase-nb.4_1] PROPOSED FOLLOW-UP: sase-n8 alias-history row helpers are still unused outside their module — I had to --epic-symbol AliasHistoryRowSpec / alias_history_empty_text / alias_history_group_header_text / alias_history_row_text under sase-n8 so just check could pass after closed-bead whitelist cleanup; n8 land should consume them in the panel or make them private.

[2026-08-16T20:38:39Z · sase-nb.4_1] PROPOSED FOLLOW-UP: closed-bead Symvision leftovers — sase-n9 family_plan_preview_cache_key / FamilyPreviewCacheKey and sase-na.4 HistoryWordCompletionMetadata were still public after those beads closed; I privatized them (in-file only) so the stale Justfile --epic-symbol entries could be removed. Confirm no remaining cross-file callers.

[2026-08-16T21:36:35Z · sase-nb.4_1--2] PROPOSED FOLLOW-UP: file-panel MagicMock helper never binds _update_body — six tests/test_file_panel.py render tests fail in isolation because _render_full_content now routes through _update_body, so panel.update is never called (test_render_static_file_result_renders_content, display_linked_diff, live_diff line count/cache, pathological cap, linked_diff rerender). Not caused by look-phase flag presentation.

[2026-08-16T21:40:10Z · sase-nb.4_1--2] PROPOSED FOLLOW-UP: test_save_atomically_replaces_existing_state patches global os.replace via config_center_state.os and counted 5 replacements (including .procs_* writes) in the escalated full suite; passes in isolation. Test isolation / global os.replace monkeypatch, not look-phase.

[2026-08-16T21:41:10Z · sase-nb.4_1--2] Look-phase visual language is in place: flag type is ⚑ / #FF875F (chip bold black on #FF875F, Rich bold #FF875F, Python cli_style == Rust ANSI_TYPE_FLAG \\x1b[38;5;209m). bead_flag_presentation renders the key chip (⚑ <key> on the type accent) and the urgency-graded countdown (live dim ⧗ 84d · v0.19.0, soon bold #FFAF00 ⧗ 12d · v0.19.0, due bold reverse DUE ⧗ +6d) on both Rich and ANSI surfaces via flag_removal_due. Derived type:flag surfaces (BEAD_TYPE_VALUES, beads_query_schema hint, BeadFilterBar completions, parse_bead_filter_query) accept flag from the type table. just check: all lint gates passed; scoped lane escalated to the full suite because Justfile epic-symbol list changed; 31523 passed, 7 failed — all unrelated (file_panel MagicMock missing _update_body; config_center_state os.replace isolation flake). Look-phase goldens plus type-presentation/filter-bar/family-preview-cache/history-word-completion: 88 passed. Two additional PROPOSED FOLLOW-UP notes recorded for those suite failures.

## Dependencies

- **Depends on:** [sase-nb.3](sase-nb.3.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-nb.6](sase-nb.6.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-nb.7](sase-nb.7.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-nb.8](sase-nb.8.md) ◐ · ⧖ 2026-08-16

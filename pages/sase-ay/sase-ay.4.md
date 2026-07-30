# Bead: sase-ay.4 — Completion panel row budget

[Bead Pages](../README.md) / [sase-ay](README.md) / sase-ay.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ay.4` · **Size:** small
**Created:** 2026-07-29 22:24:41 UTC · **Closed:** 2026-07-29 22:48:01 UTC
**Plan:** [202607/at\_reference\_completion\_menu.md](https://github.com/sase-org/sase--plans/blob/main/202607/at_reference_completion_menu.md)

## Description

panel_rows: derive the visible-row budget from the panel's real content capacity so the highlighted row and the overflow indicator are never clipped, and reserve a line for a group rule when one is rendered.

## Notes

[2026-07-29T22:48:01Z · sase-ay.4] panel_rows: added COMPLETION_PANEL_MAX_HEIGHT/BORDER_ROWS/CONTENT_ROWS mirrors plus completion_visible_rows() and completion_scroll_offset() in file_completion.py; the panel now slices with the same budget the caller uses to compute its scroll offset, reserving one content line for the '↓ N more…' indicator on overflow and another when a group rule is drawn (new group_rule flag on show_file_completions plus a _completion_group_rule_reserved() seam for the grouped @ menu). Verified: new tests in tests/ace/tui/widgets/test_prompt_completion_height.py cover the 15-candidate/last-row case (highlight is in the rendered window, content lines <= 8, panel.region.height <= CSS cap 10), the budget arithmetic, and that every selection index of a 15-row menu lands inside the window with and without a group rule; existing height reservation tests still pass. Full 'just test' run: 23877 passed, 1 pre-existing flake (tests/ace/tui/modals/test_input_collection_modal.py::test_growing_last_field_keeps_cursor_visible_in_fields_scroll, passes in isolation, unrelated to completion). No PNG golden churn — no existing snapshot menu renders more than 8 rows, so the whole visual suite passed unchanged. just check: fmt/ruff/mypy/keep-sorted/changelog/pyscripts all green; symvision fails identically on a clean stashed tree with 10 stale sase-ax --epic-symbol entries, so that failure is pre-existing and outside this phase. Deviation from the plan: MAX_VISIBLE was deleted rather than kept exported — after the refactor it had zero consumers in src/ or tests/, and 10 is no longer the row budget, so leaving it would be misleading dead code. Also corrected the now-stale 'up to 10 candidates' sentence in docs/ace.md since this change invalidated it.

## Dependencies

- **Blocks:** [sase-ay.7](sase-ay.7.md) ✓

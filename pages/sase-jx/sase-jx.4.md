# Bead: sase-jx.4 — Render the overrun mark across the AXE tab

[Bead Pages](../README.md) / [sase-jx](README.md) / sase-jx.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ye](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ye/README.md) · **Assignee:** `sase-jx.4` · **Size:** medium
**Created:** 2026-08-12 09:06:19 EDT · **Closed:** 2026-08-12 11:46:48 EDT
**Plan:** [202608/axe\_chop\_overrun\_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/axe_chop_overrun_indicator.md)

## Description

tab_indicator: paint the sidebar chop chip and lumberjack roll-up, the overview table's PACE column and advisory line, the chop detail header segment, the help guide legend, docs, and the PNG snapshots that pin all of it.

## Notes

[2026-08-12T15:45:14Z · sase-jx.4] PROPOSED FOLLOW-UP: 11 pre-existing PNG visual-snapshot goldens (test_axe_add_chooser_png_snapshot, test_axe_script_picker_png_snapshot, and 9 others in tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py/models_panel*/prompt_*/word_lookup*/glossary_preview*/updates_indicator*/jump_action*/vcs_*/at_reference_completion*/prompt_stack*/prompt_inputs*/model_completion*/artifacts_plans* etc.) fail with small non-zero pixel diffs against their committed goldens in this workspace even on a clean master checkout with no code changes — confirmed by stashing all changes and re-running. Root cause is unclear (font/fontconfig drift, Pillow/renderer version drift, or stale workspace state per the ephemeral-workspace note in CLAUDE.md); worth a dedicated investigation rather than blanket re-baselining, since a careless --sase-update-visual-snapshots run across a wide -k filter can silently bake this drift into new goldens.

[2026-08-12T15:46:18Z · sase-jx.4] PROPOSED FOLLOW-UP: AxeOutputSection.update_lumberjack_overview picks wide-vs-compact chop-table layout from _section_width(output_section), which returns None before the widget is first laid out. The very first render after switching to the AXE tab (or after a terminal resize) can therefore lock in the wide-table layout even when the settled panel width is well under _NARROW_OVERVIEW_WIDTH (60), and nothing re-renders that view on resize (no on_resize handler wired to _refresh_axe_display for the axe dashboard), so the wide content just visually wraps until the next selection change or the ~10s auto-refresh tick. Discovered while adding the PACE column in sase-jx.4 (tab_indicator phase) — the wider wide-table content (60->68 cells) made two existing narrow-terminal PNG goldens (axe_long_label_widened_120x40, axe_constrained_width_no_wrap_60x30) start rendering the wrapped wide-table text instead of the compact stacked layout. Worked around in the new axe_chop_overrun_narrow_70x36 PNG test by forcing an explicit _refresh_axe_display() call after layout settles (matching the pattern already used by test_axe_disabled_chop_row_png_snapshot), but the underlying stale-width bug is unfixed and could show real garbled output to a user who resizes their terminal while viewing the AXE lumberjack overview.

[2026-08-12T15:46:48Z · sase-jx.4] Rendered the overrun mark across all AXE tab surfaces per the tab_indicator design: shared OVERRUN_STYLES/format_overrun_ratio/overrun_chip helpers in _axe_dashboard_render.py; sidebar chop chip (worst ratio) + lumberjack roll-up chip ordered before cycles/errors chip; overview table's re-spaced PACE column (68-cell rule preserved) + compact-list chip; advisory line (single/collapsed-multi over-chop wording, intermittent second line, configured-interval suffix); chop-detail header segment gated to the newest run via level=="over"; onboarding legend line + docs/axe.md paragraph. Added/extended unit and widget tests (test_bgcmd_list_formatters.py, test_axe_dashboard_lumberjack_overview.py, test_axe_dashboard_status_section.py, test_axe_dashboard_chop_detail.py) and two new PNG snapshots (axe_chop_overrun_120x40, axe_chop_overrun_narrow_70x36), eyeballed both. Verified: just check green (all lint gates + scoped tests); just test-visual -k axe green except 11 PNG goldens confirmed pre-existing/environment-drift (fail identically on clean master, unrelated to this change) — only the 6 legitimately-affected wide-table goldens plus the 2 new snapshots were re-baselined, verified pixel-by-pixel against clean-master to avoid masking unrelated drift. Filed two PROPOSED FOLLOW-UP notes: the pre-existing PNG drift, and a stale layout-width bug in update_lumberjack_overview's wide/compact selection discovered while adding the PACE column.

[2026-08-12T15:48:01Z · sase-jx.4] Verified: just check green (14/14 gates); just test-visual -k axe green except 11 pre-existing unrelated goldens confirmed via clean-master diff; PNG overrun snapshots re-baselined and eyeballed.

## Dependencies

- **Depends on:** [sase-jx.3](sase-jx.3.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jx.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jx.4/README.md) | [sase-jx.4](sase-jx.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d4c4efd`](https://github.com/sase-org/sase/commit/d4c4efda57da358787c94801d3d8cdea038c05af) | feat(axe): render overrun indicator across AXE tab surfaces | [sase-jx.4](sase-jx.4.md) | 2026-08-12 11:49:14 EDT |

# Bead: sase-kv.2 — Icons, cell-accurate click ranges, and reflow-to-fit in PanelTabStrip

[Bead Pages](../README.md) / [sase-kv](README.md) / sase-kv.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.z6.f2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.z6.f2.md) · **Assignee:** `sase-kv.2` · **Size:** medium
**Created:** 2026-08-13 09:16:41 EDT · **Closed:** 2026-08-13 09:45:10 EDT
**Plan:** [202608/artifacts\_tab\_icons.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_tab_icons.md)

## Description

strip: give `PanelTab` an icon, render it between the number and the label, measure click ranges in terminal cells instead of characters, and add an opt-in reflow ladder that keeps every tab visible and clickable when the strip cannot fit its full render.

## Notes

[2026-08-13T13:45:10Z · sase-kv.2] Added icon: str = "" to PanelTab and reflow_to_fit: bool = False to PanelTabStrip.__init__ in src/sase/ace/tui/widgets/panel_tab_strip.py. _build_content() now renders icons (after the number/pad, before the label, styled like the shortcut) and measures every fragment via rich.cells.cell_len instead of len(text.plain), so _tab_ranges/_line_width are cell-accurate. on_resize() now also drives a reflow_to_fit ladder (full -> compact -> micro, picking the narrowest tier that fits, falling back to micro) when no compact_below/micro_below thresholds are set; thresholds still take precedence when set. In the micro tier, inactive-tab labels are dropped only when every tab has a non-empty icon. Verified: just install; just check (all lint gates incl. mypy/ruff/symvision green, scoped test lane green, exit 0); mypy directly on the file (clean); new tests in tests/ace/tui/test_panel_tab_strip_compact.py covering icon placement + empty-icon no-op, cell-accurate click ranges with a 2-cell emoji icon via pilot.click, the reflow_to_fit ladder across three terminal widths via pilot.resize_terminal, and micro-tier label-hiding gated on every tab having an icon (7/7 pass); the 3 pre-existing tests in that file plus all tests in the six other PanelTabStrip callers (test_project_management_modal_filtering.py, test_artifacts_scaffold.py, test_config_center_navigation.py, test_config_center_tabs.py, test_projects_pane.py, test_statistics_pane_interactions.py) still pass unchanged (66/66), confirming icon-less/no-reflow strips render byte-identical to before.

[2026-08-13T13:46:38Z · sase-kv.2] Added icon support, cell-accurate click ranges (rich.cells.cell_len), and reflow_to_fit ladder (full/compact/micro) to PanelTabStrip; added 4 new tests covering icon rendering, 2-cell-emoji click ranges, reflow across widths, and micro label-hiding gating. Verified via just install, just check (all lint gates + scoped tests pass), direct mypy, and full test runs of all 6 other PanelTabStrip callers (66/66 pass).

## Dependencies

- **Blocks:** [sase-kv.5](sase-kv.5.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kv.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kv.2/README.md) | [sase-kv.2](sase-kv.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2ff6a22`](https://github.com/sase-org/sase/commit/2ff6a221a11513724f7e1002aa1d4eaee6a89df1) | feat(ace): add icons, cell-accurate clicks, and fit-reflow to PanelTabStrip | [sase-kv.2](sase-kv.2.md) | 2026-08-13 09:48:12 EDT |

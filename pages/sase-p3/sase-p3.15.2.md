# Bead: sase-p3.15.2 — Stop required-plugin config from leaking into test runs

[Bead Pages](../README.md) / [sase-p3.15](sase-p3.15.md) / sase-p3.15.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-p3.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p3.land.md) · **Assignee:** `sase-p3.15.2` · **Size:** medium
**Created:** 2026-08-18 04:37:38 EDT
**Plan:** [202608/required\_plugin\_install\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202608/required_plugin_install_repair.md)

## Description

plugin-config-isolation: decide whether plugin-contributed `sase_config` layers belong in test runs, implement that decision, and restore `test_tribe_panel_display_config_png_snapshot` to a true premise.

## Notes

[2026-08-18T08:52:04Z · sase-p3.15.2] Decision: isolate plugin sase_config from the default test fixture (SASE_DISABLE_PLUGIN_CONFIG=1). Tests assert bundled defaults; real_plugin_config opts into production merge. Targeted tests prove both states; the tribe-panel visual snapshot premise stays true.

[2026-08-18T09:14:20Z · sase-p3.15.2--2] PROPOSED FOLLOW-UP: flake tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes — just check (xdist scoped suite) asserted scroll_y==0 after G while max_scroll_y==190; 8/8 serial reruns passed. Likely a late LogsPane load worker with reset_scroll=True restoring the detail pane after G. Not caused by plugin-config isolation.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.15.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p3.15.2.md) | [sase-p3.15.2](sase-p3.15.2.md) | 0 |

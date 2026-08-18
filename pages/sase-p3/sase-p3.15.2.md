# Bead: sase-p3.15.2 — Stop required-plugin config from leaking into test runs

[Bead Pages](../README.md) / [sase-p3.15](sase-p3.15.md) / sase-p3.15.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-p3.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p3.land.md) · **Assignee:** `sase-p3.15.2` · **Size:** medium
**Created:** 2026-08-18 04:37:38 EDT · **Closed:** 2026-08-18 06:00:13 EDT
**Plan:** [202608/required\_plugin\_install\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202608/required_plugin_install_repair.md)

## Description

plugin-config-isolation: decide whether plugin-contributed `sase_config` layers belong in test runs, implement that decision, and restore `test_tribe_panel_display_config_png_snapshot` to a true premise.

## Notes

[2026-08-18T08:52:04Z · sase-p3.15.2] Decision: isolate plugin sase_config from the default test fixture (SASE_DISABLE_PLUGIN_CONFIG=1). Tests assert bundled defaults; real_plugin_config opts into production merge. Targeted tests prove both states; the tribe-panel visual snapshot premise stays true.

[2026-08-18T09:14:20Z · sase-p3.15.2--2] PROPOSED FOLLOW-UP: flake tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes — just check (xdist scoped suite) asserted scroll_y==0 after G while max_scroll_y==190; 8/8 serial reruns passed. Likely a late LogsPane load worker with reset_scroll=True restoring the detail pane after G. Not caused by plugin-config isolation.

[2026-08-18T09:48:26Z · sase-p3.15.2--3] Incidental unblockers for just test-visual (not isolation): (1) refreshed agents_task_bead_notes_120x40.png so the landed Task Type row is in the golden; (2) FakeyRetryHarness.run_spawn_retry_chain now returns timestamp on the spawn mock so spawn_retry_agent can read result.timestamp.

[2026-08-18T10:00:13Z · sase-p3.15.2--4] Default fixture isolates plugin sase_config (SASE_DISABLE_PLUGIN_CONFIG=1 unless a test requests real_plugin_config). Targeted merge test with real_plugin_config covers production merge; tribe-panel visual snapshot passed unchanged. just check and just test-visual green (scoped suite escalated after conftest; 712 visual passed, 1 skipped).

[2026-08-18T10:01:48Z · sase-p3.15.2--4] Default fixture isolates plugin sase_config; targeted merge test with real_plugin_config covers production merge; tribe-panel visual snapshot passed unchanged; just check and just test-visual green (712 passed, 1 skipped).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.15.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p3.15.2.md) | [sase-p3.15.2](sase-p3.15.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3485cb3`](https://github.com/sase-org/sase/commit/3485cb37d9705c4a687b410e1a91df795456d82c) | test: isolate plugin sase\_config from the default fixture | [sase-p3.15.2](sase-p3.15.2.md) | 2026-08-18 06:02:29 EDT |

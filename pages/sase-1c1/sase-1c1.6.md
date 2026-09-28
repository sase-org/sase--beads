# Bead: sase-1c1.6 — Repair Admin Center tab-model fallout from the Tools pane

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.6` · **Size:** medium
**Created:** 2026-09-28 07:09:31 EDT · **Closed:** 2026-09-28 08:20:30 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

admin-center-tabs: reconcile the 6 Admin Center and Config Center tests (tab order, count, digit shortcuts, resume, cached open, blocked write) with the Tools tab added by sase-1bt.10, fixing the product wherever a documented invariant broke.

## Notes

[2026-09-28T12:20:30Z · sase-1c1.6] Reconciled the 6 mapped Admin Center/Config Center tests with the Tools tab (sase-1bt.10, digit 7, label alphabetically before Updates which shifted to digit 8). No product defect: the tab order stayed alphabetical (config, logs, machines, procs, projects, statistics, tools, updates) and digit routing already matched the registry (test_config_hub_pane_navigation.py::test_home_digits_stop_at_eight already expected this). All 6 were stale test expectations from before the Tools tab landed:
- test_log_panel_keymap.py::test_admin_center_tabs_are_alphabetical_by_label: added "tools" to the hardcoded expected tuple.
- test_admin_center_selection_resume.py[updates] (NoMatches PluginsBrowserPane): updates case's tab_key was "7" (now tools); changed to "8".
- test_xprompt_browser_load_keymap.py::test_list_focused_out_of_range_digits_are_no_ops ('updates' == 'config'): digit "8" is now in-range (updates); out-of-range set changed from (8,9,0) to (9,0).
- test_plugins_browser_pane_loading.py::test_config_center_cycles_seven_tabs (wait_for timeout): renamed to test_config_center_cycles_all_tabs and inserted "tools" into the cycle sequence between statistics and updates.
- test_config_center_resume.py::test_blocked_write_keeps_navigation_responsive_and_persists_latest (wait_for timeout): same digit shift, "7"->"8" for updates.
- test_plugins_browser_pane_cached_open.py (3 == 2): did not reproduce. Ran serially x3 and under xdist (-n 4, mixed with the other 5 admin-center files) with all passing; a heavier -n 16 stress run alongside ~6 other concurrent sase agent workspaces on the shared host stalled past 5 minutes on host contention, not a hang in this suite (no orphaned pytest process afterward). Treating as a non-reproducing flake at this HEAD.

Verified: all 6 mapped tests green (88 passed under tests/ace/tui/test_admin_center_selection_resume.py + test_log_panel_keymap.py + test_xprompt_browser_load_keymap.py + test_plugins_browser_pane_loading.py + test_plugins_browser_pane_cached_open.py + test_config_center_resume.py, serial and xdist -n4). sase tool run check (ce31d073485c645ec6051026eb22cb64) passed with verdict no_new_failures: 2 KNOWN failures remain (test_config_schema.py::test_default_config_matches_public_schema for ace.keymaps.tool_runs, and test_timezone_display_guard.py::test_no_system_clock_display_sites), both owned by the contract-drift phase, not this one. sase bead epic-symbols sase-1c1.6 reported no --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1c1.12](sase-1c1.12.md) ◐ · ⧖ 2026-09-28
- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1c1.6/README.md) | [sase-1c1.6](sase-1c1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ead97d5`](https://github.com/sase-org/sase/commit/ead97d5cc48af2c083075e2f12b79c0c5d6f9ed2) | fix(ace): reconcile Admin Center tab tests with the Tools tab (sase-1c1.6) | [sase-1c1.6](sase-1c1.6.md) | 2026-09-28 08:21:52 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1c1.6][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1c1.6/README.md

<!-- sase:referenced-by:end -->

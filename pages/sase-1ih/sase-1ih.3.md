# Bead: sase-1ih.3 — Top-bar tools and bg split with tab-independent glance refresh

[Bead Pages](../README.md) / [sase-1ih](README.md) / sase-1ih.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.43.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.43.linker.w0.md) · **Assignee:** `sase-1ih.3` · **Size:** medium
**Created:** 2026-10-08 18:31:55 EDT · **Closed:** 2026-10-08 23:47:30 EDT
**Plan:** [202610/tools\_bg\_split\_tool\_run\_visibility.md](https://github.com/sase-org/sase--plans/blob/main/202610/tools_bg_split_tool_run_visibility.md)

## Description

top-bar-tools-bg: carrier classifier and the bg/tool/monitor/update partition; new ToolsIndicator (live, silent, bare-monitor chips, tooltip, all-projects click); ProcIndicator becomes `bg:`; the glance probe runs on every tab with stale and fallback states; Procs header ⚒ chip; top-bar docs, tests and goldens.

## Notes

[2026-10-09T03:47:02Z · sase-1ih.3--3] PROPOSED FOLLOW-UP: full `sase tool run check` has 3 KNOWN pre-existing failures unrelated to top-bar tools/bg split (witnesses 655ae19c0fe475650a406c7193ac8f2c directive %auto description, 4c192e4ff82df1ca0ecefd03afabfbae bead Tab walk, 0444682d32b8b4a6ecfb63dddf7e8469 macro xprompt string in tests/test_plugin_commands_mount.py); none of the failing files are touched by this phase

[2026-10-09T03:47:30Z · sase-1ih.3--3] top-bar tools:/bg: split landed; symvision clean; 56 targeted tests green (gear lanes, procs header, tool_runs_top_bar, top_bar_indicators/order, proc_indicator, top_bar_group); full goldens refreshed for tools/bg split; full check has only 3 KNOWN pre-existing failures unrelated to this phase

## Dependencies

- **Depends on:** [sase-1ih.1](sase-1ih.1.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1ih.4](sase-1ih.4.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ih.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ih.3.md) | [sase-1ih.3](sase-1ih.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c04b04d`](https://github.com/sase-org/sase/commit/c04b04d9e6a493c9182c44737ff3ca6cb9ff15bf) | feat(ace-tui): split top-bar tools/bg indicators with privatized carriers | [sase-1ih.3](sase-1ih.3.md) | 2026-10-08 23:50:23 EDT |

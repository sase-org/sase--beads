# Bead: sase-o9.3 — Blue and orange gear counts in the tab header

[Bead Pages](../README.md) / [sase-o9](README.md) / sase-o9.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04g.md) · **Assignee:** `sase-o9.3` · **Size:** small
**Created:** 2026-08-17 06:54:28 EDT · **Closed:** 2026-08-17 07:39:18 EDT
**Plan:** [202608/procs\_tab\_monitor\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/procs_tab_monitor_support.md)

## Description

header-gear-counts: extract the top-bar gear chip into a shared helper and render scope-aware running plain-proc and monitor counts in the Procs tab title.

## Notes

[2026-08-17T11:35:31Z · sase-o9.3] PROPOSED FOLLOW-UP: `just check`'s symvision lint gate fails on master (pre-existing, unrelated to this phase): --epic-symbol entries for closed bead sase-o8.2 ("CommonPlaceholderIndex", "load_common_placeholder_index") are stale and must be removed from the symvision epic-symbol whitelist in the justfile per sase/memory/symvision.md epic whitelist cleanup rules.

[2026-08-17T11:39:18Z · sase-o9.3] Extracted the top-bar gear chip into src/sase/ace/tui/proc_gear_chips.py (gear_chip(), PROC_GEAR_HUE, MONITOR_GEAR_HUE re-exported from monitor_state); ProcIndicator/MonitorIndicator now call it and their top-bar rendering is byte-identical (existing test_proc_indicator.py passes unchanged). _title_text() in procs_pane_selection.py now returns a Rich Text with scope-filtered blue/orange gear counts (N=active non-monitor rows, M=active monitor rows, R=N+M) using is_active()/is_monitor_shell_row() over self._tasks, with the zero-lane dim variant always shown (never hidden) per design principle 4. Verified via: new tests/ace/tui/test_proc_gear_chips.py (chip builder), tests/ace/tui/test_procs_pane_header_counts.py (split counts, zero-state dim rendering, finished-monitor exclusion, scope-toggle-with-'a' movement), and the full existing tests/ace/tui/test_procs_pane_store.py + test_procs_pane_selection.py + widgets/test_proc_indicator.py suites (26 tests, all pass). just check green except the pre-existing, unrelated symvision stale-epic-symbol failure (sase-o8.2 closed-bead whitelist entries), reproduced identically on master before my changes and logged as a PROPOSED FOLLOW-UP note on this bead. test-scoped escalated to the full 1244-test suite (stale coverage baseline) and all passed.

[2026-08-17T11:39:57Z · sase-o9.3] Extracted shared gear-chip rendering into src/sase/ace/tui/proc_gear_chips.py (gear_chip(), PROC_GEAR_HUE, MONITOR_GEAR_HUE) reused by ProcIndicator/MonitorIndicator with byte-identical top-bar output. Updated _title_text() in procs_pane_selection.py to render scope-aware blue/orange gear counts alongside existing running/done totals, always showing both lanes (dimmed when zero). Added test_proc_gear_chips.py and test_procs_pane_header_counts.py covering split counts, zero-state, finished-monitor exclusion, and scope toggle; extended _procs_pane_helpers.py to pass origin/shell_name through to ObservedProc. Verified via just check: full lint/test gate lineup green except a pre-existing, unrelated symvision stale-whitelist failure on master (confirmed via git stash), logged as PROPOSED FOLLOW-UP on this bead for the epic land agent to triage.

## Dependencies

- **Depends on:** [sase-o9.1](sase-o9.1.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-o9.5](sase-o9.5.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-o9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o9.3/README.md) | [sase-o9.3](sase-o9.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6bd5d57`](https://github.com/sase-org/sase/commit/6bd5d57229493bb2db0d1d6b762ff7acc153d3a3) | feat(ace-tui): split blue/orange gear counts into the procs pane header | [sase-o9.3](sase-o9.3.md) | 2026-08-17 07:40:37 EDT |

# Bead: sase-qd.4 — The set-current keypress

[Bead Pages](../README.md) / [sase-qd](README.md) / sase-qd.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06w](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06w.md) · **Assignee:** `sase-qd.4` · **Size:** medium
**Created:** 2026-08-18 18:14:40 EDT · **Closed:** 2026-08-18 20:07:12 EDT
**Plan:** [202608/projects\_tab\_current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/projects_tab_current_project.md)

## Description

set-action: bind `set_current_project` (default `c`) in the Projects sub-tab, run core-set's write on a thread worker with cheap in-memory pre-checks, report every outcome honestly in the status line and a notification, and refresh the top-bar chip immediately instead of waiting out its poll.

## Notes

[2026-08-19T00:06:32Z · sase-qd.4] PROPOSED FOLLOW-UP: just check toobig — tests/_suite_gate.py is 1197 lines (limit 1000) after f7e6acbf6; whole-repo just check is red for every agent on this tree and this phase did not touch that file.

[2026-08-19T00:06:47Z · sase-qd.4] PROPOSED FOLLOW-UP: flake test_logs_tab_g_and_shift_g_scroll_detail_extremes — failed under xdist in the escalated scoped run (scroll_y stayed 0 while max_scroll_y was 190); same node passed serially on this tree. Unrelated to the Projects set-current keypress.

[2026-08-19T00:07:12Z · sase-qd.4] Projects tab c/set_current_project now runs set_current_project on a thread worker after in-memory pre-checks (no selection, disabled+enable-a warning, non-launchable, already current). The four write outcomes set status+notify (information/warning/error); a set restarts the pane resolve and calls CurrentProjectIndicator.invalidate(), which bypasses the 0.5s peek floor and no-ops while a resolve is in flight. A missing chip is ignored. Verified: 27 new/updated tests pass; ruff/mypy/symvision pass; no leftover --epic-symbol entries. just check itself is red on pre-existing tests/_suite_gate.py toobig (1197>1000) and one unrelated logs-pane flake under xdist (passed on rerun).

[2026-08-19T00:08:34Z · sase-qd.4] Projects tab c/set_current_project runs set_current_project on a thread worker after in-memory pre-checks (no selection, disabled+enable-a warning, non-launchable, already current). The four write outcomes set status+notify (information/warning/error); a set restarts the pane resolve and calls CurrentProjectIndicator.invalidate(), which bypasses the 0.5s peek floor and no-ops while a resolve is in flight. A missing chip is ignored. Verified: 27 new/updated tests pass; ruff/mypy/symvision pass; no leftover --epic-symbol entries. just check itself is red on pre-existing tests/_suite_gate.py toobig (1197>1000) and one unrelated logs-pane flake under xdist (passed on rerun).

## Dependencies

- **Depends on:** [sase-qd.1](sase-qd.1.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-qd.3](sase-qd.3.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-qd.5](sase-qd.5.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qd.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qd.4/README.md) | [sase-qd.4](sase-qd.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5d7812a`](https://github.com/sase-org/sase/commit/5d7812a2c39260ce8aba72bfba31bac1d0c43ef5) | feat(ace): set current project from the Projects tab | [sase-qd.4](sase-qd.4.md) | 2026-08-18 20:09:18 EDT |

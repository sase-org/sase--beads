# Bead: sase-100.3 — Gesture rewiring behind the refresh\_panel flag

[Bead Pages](../README.md) / [sase-100](README.md) / sase-100.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0kb` · **Assignee:** `sase-100.3` · **Size:** medium
**Created:** 2026-09-12 14:57:47 EDT · **Closed:** 2026-09-13 06:48:57 EDT
**Plan:** [202609/refresh\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/refresh_panel.md)

## Description

wire: create the sunset refresh_panel flag, route R and `,y` through the panel when it is on, execute each chosen option, and keep today's direct gestures as the off branch.

## Notes

[2026-09-13T10:48:14Z · sase-100.3--1] PROPOSED FOLLOW-UP: tests/test_axe_chop_output_contract.py::test_managed_tmp_reap_emits_{noop,action}_summary fail because counters now include pressure_available_bytes and pressure_recovery_available_bytes — leftover from feat(chop) pressure reaping, unrelated to refresh_panel.

[2026-09-13T10:48:57Z · sase-100.3--1] Sunset refresh_panel flag (sase-105) both-states: R opens RefreshPanelModal when on and immediately refreshes when off; ,y migrates to the panel (cursor on full_history, banner set) when on and calls full-history directly when off. full_history works from Artifacts/Axe; usage runs off the UI thread; everything zeroes _last_full_sanity_refresh before the sweep. Footer/palette/help omit ,y when on and keep it when off. Tab labels no longer dispatch on ref:. Existing R-to-refresh AcePage tests confirm the panel (R then r). tests/ace/tui/test_refresh_panel_dispatch.py plus the previously failing TUI/contract subset passed (142). epic-symbols sase-100.3 is clean. ruff/toobig clean. just check still has 6 unrelated SDD git-identity failures (noted on sase-100.2) and 2 chop counter extras (PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-100.2](sase-100.2.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-100.4](sase-100.4.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-100.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-100.3.md) | [sase-100.3](sase-100.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a12a1ab`](https://github.com/sase-org/sase/commit/a12a1abdf6b4183b2e1cdef66afe656cb5889258) | feat(ace): wire R and ,y through the Refresh panel | [sase-100.3](sase-100.3.md) | 2026-09-13 06:51:33 EDT |

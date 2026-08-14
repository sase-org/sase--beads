# Bead: sase-lh.5 — Rename the ACE Tasks pane and Admin Center tab identifier to procs

[Bead Pages](../README.md) / [sase-lh](README.md) / sase-lh.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.000](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.000.md) · **Assignee:** `sase-lh.5` · **Size:** medium
**Created:** 2026-08-13 17:20:21 EDT · **Closed:** 2026-08-13 21:08:34 EDT
**Plan:** [202608/background\_tasks\_to\_procs.md](https://github.com/sase-org/sase--plans/blob/main/202608/background_tasks_to_procs.md)

## Description

tui-pane: rename the `tasks_pane*` and `tasks_store_rows` modules and `TasksPane` to their proc spellings, move the Admin Center tab identifier from `tasks` to `procs` with persisted-state migration, and rename the `#tasks-*` DOM ids and their `styles.tcss` selectors, without changing displayed text.

## Notes

[2026-08-14T00:40:40Z · sase-lh.5] PROPOSED FOLLOW-UP: `sase monitor start` fails with FamilyAttachError ("Cannot create agent family 'sase-lh': resolved parent is named 'sase-lh.8'.") when invoked from a phase-bead workspace whose newest agent belongs to a different phase (sase-lh.8) of the same epic. Reproduced via: sase monitor start --command "just check" --reason "..." --timeout 20m --next "..." while working sase-lh.5. src/sase/agent/_family_promotion.py:131 raises when promote_agent_to_family resolves a parent name that does not match the requested family. Investigate promote_agent_to_family/_family_promotion.py so monitor start works from any phase bead of a multi-phase epic, not just the newest one.

[2026-08-14T01:08:09Z · sase-lh.5] PROPOSED FOLLOW-UP: tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes is flaky under CPU contention (failed once in a `just check` run on a heavily loaded shared host with several concurrent agent test suites, passed immediately in isolation; file has no diff on this branch). The G/shift-G scroll-to-extreme assertion likely races a layout/scroll timing window under load. Investigate making it robust to contention (e.g. wait_for polling instead of a single post-press assertion).

[2026-08-14T01:08:34Z · sase-lh.5] Renamed tasks_pane*/tasks_store_rows modules to procs_pane*/procs_store_rows and TasksPane to ProcsPane; moved the Admin Center tab id tasks->procs in config_center_catalog.py (factory renamed, class-name string updated) and config_center_session.py (TasksSessionState->ProcsSessionState); added a read-side migration in config_center_state.py mapping persisted tasks->procs with test coverage; renamed all #tasks-* DOM ids/styles.tcss selectors and QuitConfirmModal #quit-confirm-tasks/.quit-confirm-task-card to their procs spellings; git mv'd and rewrote all corresponding test files and PNG goldens without re-rendering pixels. Displayed text (tab label 'Tasks', pane title/hints, command palette 'Open tasks panel') deliberately left untouched, matching the labels phase split. Verified: just check (2887-29841 tests passed across two full runs; only failures were pre-existing/unrelated flakes on this shared host - test_logs_pane.py scroll test passes in isolation with no diff, and axe_constrained_width_no_wrap PNG snapshot has no diff on this branch) and just test-visual (670 passed, 1 skipped, only the same unrelated axe_layout failure). Fixed one stale #tasks assertion in test_config_center_navigation.py that the rename had missed.

## Dependencies

- **Depends on:** [sase-lh.2](sase-lh.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-lh.6](sase-lh.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lh.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.5/README.md) | [sase-lh.5](sase-lh.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8ca241c`](https://github.com/sase-org/sase/commit/8ca241c59854236f184f776dacfd5536132645f7) | refactor(ace): rename the ACE Tasks pane and Admin Center tab id to procs | [sase-lh.5](sase-lh.5.md) | 2026-08-13 21:09:21 EDT |

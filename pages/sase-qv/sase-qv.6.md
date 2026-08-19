# Bead: sase-qv.6 — Procs tab monitor status chip

[Bead Pages](../README.md) / [sase-qv](README.md) / sase-qv.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07k](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07k.md) · **Assignee:** `sase-qv.6` · **Size:** small
**Created:** 2026-08-19 09:14:33 EDT · **Closed:** 2026-08-19 12:21:46 EDT
**Plan:** [202608/monitor\_custom\_statuses.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_custom_statuses.md)

## Description

procs: resolve each monitor proc row's status pair from the loaded agent rows and render the effective label as an accent-colored chip in the Admin Center Procs tab row labels and output header.

## Notes

[2026-08-19T16:21:24Z · sase-qv.6] PROPOSED FOLLOW-UP: just check symvision gate fails on master unrelated to this phase — Justfile has 11 stale --epic-symbol "sase-qt.6(...)" entries for a closed bead (sase-qt.6), blocking just check for all agents. Re-key those lines to sase-qt.8 (open, same epic, blocked by sase-qt.6) or remove if symbols no longer need coverage.

[2026-08-19T16:21:46Z · sase-qv.6] Verified: resolved each monitor row's status pair from loaded agent rows and rendered the effective label as an accent-colored MonitorStatusChip in task_row_label and output_header (procs_pane_render.py), wired via _resolve_monitor_statuses in procs_pane_selection.py and procs_pane_actions.py/procs_pane.py. ruff format/check clean, mypy clean on touched files, 32/32 unit tests pass (test_procs_pane_render.py, test_procs_pane_selection.py). sase bead epic-symbols sase-qv.6 reports no leftover --epic-symbol entries. just check's symvision gate fails but only due to a pre-existing, unrelated stale sase-qt.6 entry (confirmed reproducible on master before this change via git stash); filed as PROPOSED FOLLOW-UP note on this bead.

## Dependencies

- **Depends on:** [sase-qv.3](sase-qv.3.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qv.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.6/README.md) | [sase-qv.6](sase-qv.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4bca0e6`](https://github.com/sase-org/sase/commit/4bca0e66aabe4ac8a912cd29519f1862cf0d50af) | feat(tui): render monitor status chip in Procs tab rows | [sase-qv.6](sase-qv.6.md) | 2026-08-19 12:22:51 EDT |

# Bead: sase-bg.7 — sase bead work for task beads and detached submitter

[Bead Pages](../README.md) / [sase-bg](README.md) / sase-bg.7

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bg.7` · **Size:** large
**Created:** 2026-07-30 22:55:44 UTC · **Closed:** 2026-07-31 00:43:36 UTC
**Plan:** [202607/task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202607/task_beads.md)

## Description

task-launch: route task bead targets through sase bead work with single-commit in-progress marking, rollback, dry-run, model routing including a task_worker alias, single-segment prompt composition ending in bd/work_task, and a task_launch.py detached submitter mirroring epic_launch.py.

## Notes

[2026-07-31T00:43:36Z · sase-bg.7] Implemented task-bead work launch orchestration, deterministic cleanup/checkpoint/rollback behavior, detached deduplicated submission, task_worker model routing, CLI/help/JSON output, and focused coverage. Verified 31 focused task tests, 21 existing work-dispatch tests, 160 model-alias tests, formatting, lint, Symvision, mypy, committed-plan validation, and git diff --check. Full suite completed with 24,626 passes; two unrelated contention flakes passed in isolation. just check remains blocked only by unrelated external validation state: stale generated provider skills in linked chezmoi and missing plan-sidecar target 202607/commit_vars_finalizer.md.

## Dependencies

- **Depends on:** [sase-bg.2](sase-bg.2.md) ✓
- **Depends on:** [sase-bg.6](sase-bg.6.md) ✓
- **Blocks:** [sase-bg.8](sase-bg.8.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bg.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-bg.7.md) | [sase-bg.7](sase-bg.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`879af9b`](https://github.com/sase-org/sase/commit/879af9b0831fa59a0bccaf580d11f6afd26ffb2c) | feat(bead): launch standalone task workers | [sase-bg.7](sase-bg.7.md) | 2026-07-31 00:45:26 |

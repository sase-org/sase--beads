# Bead: sase-9v.8 — Move legacy epic-approval preflight off the ACE event loop

[Bead Pages](../README.md) / [sase-9v](README.md) / sase-9v.8

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9v.8` · **Size:** small
**Created:** 2026-07-26 15:32:30 UTC
**Plan:** [sase/repos/plans/202607/bead\_review\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/bead_review_hardening.md)

## Description

tui_epic_approval_offload: run the legacy plan-approval modal's epic-launch preflight and submission through the tracked-task pattern the modern gate path already uses, so store materialization and lock waits never block the Textual event loop.

## Notes

Implemented legacy epic approval offload: the response file is still written immediately, then prepare_epic_launch runs via _submit_tracked_task as a tracked launch task with completion-time error notification. Added regression coverage that the preflight is not called from the dismiss callback and existing epic launch success/failure behavior routes through the task. Verification: focused plan approval tests passed; ruff/mypy on touched source passed; just check format/lint/SASE validation passed, but full pytest runs hit unrelated load-sensitive failures that passed when rerun directly.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9v.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9v.8/README.md) | [sase-9v.8](sase-9v.8.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0c051a0`](https://github.com/sase-org/sase/commit/0c051a009d8ca740c801bb9d1ef9fe3281ba94c3) | fix(tui): offload legacy epic approval launch (sase-9v.8) | [sase-9v.8](sase-9v.8.md) | 2026-07-26 16:36:05 |

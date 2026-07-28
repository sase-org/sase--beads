# Bead: sase-95.8 — End-to-end transparency exercise

[Bead Pages](../README.md) / [sase-95](README.md) / sase-95.8

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-95.8` · **Size:** small
**Created:** 2026-07-25 12:07:53 UTC
**Plan:** [202607/background\_tasks.md](https://github.com/sase-org/sase--plans/blob/main/202607/background_tasks.md)

## Description

'End-to-end transparency exercise' section: drive a real epic approval and a plain `sase task run` across CLI and TUI surfaces, then fix what the exercise surfaces.

## Notes

Exercised sase task list/show/run with no-wait, --wait, --json, --json --wait, nonzero exit, durable kill, retention pruning in isolated SASE_HOME, supervisor SIGKILL reconciliation, and a non-bead-creating epic-launch task against a missing plan. Found and fixed a TUI mirror race where progress polling could write a terminal error before the explicit successful finish update; added regression coverage in tests/ace/tui/test_task_mirror.py. Focused task/epic suites pass. Full just check reached the full test stage but failed in unrelated suite-gate/diff-cache tests that reproduce outside this change.

## Dependencies

- **Depends on:** [sase-95.5](sase-95.5.md) ✓
- **Depends on:** [sase-95.6](sase-95.6.md) ✓
- **Depends on:** [sase-95.7](sase-95.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-95.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-95.8/README.md) | [sase-95.8](sase-95.8.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`54e0978`](https://github.com/sase-org/sase/commit/54e097800228f0779af2d98db6717a55efaccec8) | fix(tui): avoid terminal task mirror races (sase-95.8) | [sase-95.8](sase-95.8.md) | 2026-07-25 19:12:07 |

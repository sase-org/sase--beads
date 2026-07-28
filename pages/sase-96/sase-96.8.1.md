# Bead: sase-96.8.1 — Route the terminal-smoke lane through the pytest runner

[Bead Pages](../README.md) / [sase-96.8](sase-96.8.md) / sase-96.8.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-96.8.1` · **Size:** small
**Created:** 2026-07-25 18:15:17 UTC
**Plan:** [202607/managed\_tmp\_reaping.md](https://github.com/sase-org/sase--plans/blob/main/202607/managed_tmp_reaping.md)

## Description

'Route the terminal-smoke lane through the pytest runner' section: give tools/run_pytest a serial terminal-smoke mode, point the just recipe at it instead of a direct pytest invocation, and make the leak guard compare snapshots only when the runner has redirected the temp root. This work was authored during the sase-96 landing verification and may already be committed; confirm it is present and complete rather than redoing it.

## Notes

Implemented terminal-smoke runner mode, Justfile routing, and redirected-temp leak-guard gating. Focused tests passed: tools/run_pytest fast tests/test_run_pytest_tool.py tests/test_tmp_leak_guard.py -q (61 passed) and tools/run_pytest terminal-smoke tests/ace/tui/terminal_smoke --collect-only -q (1 collected). Full just check reached test stage but failed unrelated/pre-existing tests: date-sensitive plan/vcs canonical-query fixtures under current date 2026-07-26, known test_diff_cache pollution noted in the design, and an unrelated ACE PNG golden mismatch. The actual terminal-smoke PTY test also fails under both the old direct pytest invocation and the new runner path waiting for terminal_feature, while the new runner path does redirect tmp_path under /var/tmp.

## Dependencies

- **Blocks:** [sase-96.8.9](sase-96.8.9.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-96.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-96.8.1/README.md) | [sase-96.8.1](sase-96.8.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0417b41`](https://github.com/sase-org/sase/commit/0417b415d8c7b30c9e1c94e2c5cebe3e2a3aa31c) | build: route terminal smoke through pytest runner (sase-96.8.1) | [sase-96.8.1](sase-96.8.1.md) | 2026-07-26 10:36:18 |

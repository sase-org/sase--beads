# Bead: sase-96.8.3 — Stop the test suite from writing into the developer's managed temp root

[Bead Pages](../README.md) / [sase-96.8](sase-96.8.md) / sase-96.8.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Size:** medium
**Created:** 2026-07-25 18:15:37 UTC · **Closed:** 2026-07-25 19:35:41 UTC
**Plan:** [202607/managed\_tmp\_reaping.md](https://github.com/sase-org/sase--plans/blob/main/202607/managed_tmp_reaping.md)

## Description

'Stop the test suite from writing into the developer's managed temp root' section: make get_sase_managed_tmpdir sandbox-aware under pytest by reusing sase-9l's state_write_guard and SASE_PYTEST_SANDBOX_DIR, fail closed when no sandbox is published, and extend the leak guard to watch the managed root. A 31-test run currently adds six directories to the real root, unseen by either guard.

## Dependencies

- **Blocks:** [sase-96.8.7](sase-96.8.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-96.8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-96.8.3/README.md) | [sase-96.8.3](sase-96.8.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`bd16432`](https://github.com/sase-org/sase/commit/bd16432c966c92dc66f4a31489eef8214f4d73a1) | fix: stop the test suite from writing into the managed temp root (sase-96.8.3) | [sase-96.8.3](sase-96.8.3.md) | 2026-07-25 19:37:20 |

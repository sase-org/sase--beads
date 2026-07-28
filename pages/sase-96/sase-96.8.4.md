# Bead: sase-96.8.4 — Reap everything stale under the pytest scratch root

[Bead Pages](../README.md) / [sase-96.8](sase-96.8.md) / sase-96.8.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-96.8.4` · **Size:** small
**Created:** 2026-07-25 18:15:51 UTC · **Closed:** 2026-07-26 10:33:06 UTC
**Plan:** [202607/managed\_tmp\_reaping.md](https://github.com/sase-org/sase--plans/blob/main/202607/managed_tmp_reaping.md)

## Description

'Reap everything stale under the pytest scratch root' section: widen tools/run_pytest's reaper so it prunes any stale top-level entry under the workspace-private scratch root rather than only pytest-<N> and garbage-* under pytest-of-*, which today leaves 99 inline-snapshot-* directories unreclaimed.

## Dependencies

- **Blocks:** [sase-96.8.9](sase-96.8.9.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-96.8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-96.8.4/README.md) | [sase-96.8.4](sase-96.8.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`88cb087`](https://github.com/sase-org/sase/commit/88cb0876d1990363dae046381a6ce22eab5de516) | fix: reap stale pytest scratch entries (sase-96.8.4) | [sase-96.8.4](sase-96.8.4.md) | 2026-07-25 18:54:50 |

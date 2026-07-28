# Bead: sase-80.2 — Pytest lifecycle guard and daemon env hygiene

[Bead Pages](../README.md) / [sase-80](README.md) / sase-80.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-80.2`
**Created:** 2026-07-20 01:56:58 UTC
**Plan:** [202607/axe\_test\_isolation\_leak.md](https://github.com/sase-org/sase--plans/blob/main/202607/axe_test_isolation_leak.md)

## Description

'Pytest lifecycle guard and daemon env hygiene' section: refuse axe daemon start/stop/restart under pytest without an explicit override, and scrub pytest variables from the spawned daemon environment.

## Notes

COMMIT: 92db539e4

## Dependencies

- **Depends on:** [sase-80.1](sase-80.1.md) ✓
- **Blocks:** [sase-80.3](sase-80.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-80.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-80.2/README.md) | [sase-80.2](sase-80.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`969970b`](https://github.com/sase-org/sase/commit/969970bcb7a7cdd757cb78bcfe5eaf2bdef9e2e9) | fix(axe): guard daemon lifecycle under pytest (sase-80.2) | [sase-80.2](sase-80.2.md) | 2026-07-20 12:35:53 |

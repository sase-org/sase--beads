# Bead: sase-86.3 — Top-offender test optimizations

[Bead Pages](../README.md) / [sase-86](README.md) / sase-86.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-86.3` · **Size:** medium
**Created:** 2026-07-20 14:59:59 UTC
**Plan:** [202607/fast\_test\_suite.md](https://github.com/sase-org/sase--plans/blob/main/202607/fast_test_suite.md)

## Description

'Top-offender test optimizations' section: fix the slowest individual tests surfaced by the durations baseline - repo-scanning audit tests, zoom-panel and keymaps e2e files, and visual PNG snapshot hot spots - keeping every test and assertion intact.

## Notes

COMMIT: 2e5b56260

## Dependencies

- **Depends on:** [sase-86.2](sase-86.2.md) ✓
- **Blocks:** [sase-86.6](sase-86.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-86.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-86.3/README.md) | [sase-86.3](sase-86.3.md) | 1 |
| [bbugyi200.athena.sase-86.3--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-86.3.md#member-code) | [sase-86.3](sase-86.3.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a0a09b2`](https://github.com/sase-org/sase/commit/a0a09b22a176d4449acbead9b7b6051efc9c8f81) | perf(test): reduce top-offender suite runtime (sase-86.3) | [sase-86.3](sase-86.3.md) | 2026-07-20 17:20:55 |

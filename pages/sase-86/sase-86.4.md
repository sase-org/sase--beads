# Bead: sase-86.4 — Distribution scheduling and stragglers

[Bead Pages](../README.md) / [sase-86](README.md) / sase-86.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-86.4` · **Size:** medium
**Created:** 2026-07-20 15:00:01 UTC
**Plan:** [202607/fast\_test\_suite.md](https://github.com/sase-org/sase--plans/blob/main/202607/fast_test_suite.md)

## Description

'Distribution scheduling and stragglers' section: evaluate xdist worksteal distribution against the current loadfile mode, prove within-file order independence or fall back to splitting straggler files, and eliminate the end-of-run tail.

## Notes

COMMIT: b29185149

## Dependencies

- **Depends on:** [sase-86.1](sase-86.1.md) ✓
- **Blocks:** [sase-86.6](sase-86.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-86.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-86.4/README.md) | [sase-86.4](sase-86.4.md) | 1 |
| [bbugyi200.athena.sase-86.4--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-86.4.md#member-code) | [sase-86.4](sase-86.4.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`8e544a3`](https://github.com/sase-org/sase/commit/8e544a398f7f733dfe92245b1941aee7813e499e) | perf(tests): distribute parallel tests with work stealing (sase-86.4) | [sase-86.4](sase-86.4.md) | 2026-07-20 17:02:45 |

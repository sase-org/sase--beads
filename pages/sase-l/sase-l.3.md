# Bead: sase-l.3 — Phase 3 — Fix slow tests in test\_agent\_launch\_repeat.py

[Bead Pages](../README.md) / [sase-l](README.md) / sase-l.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-24 00:32:49 UTC · **Closed:** 2026-04-24 01:07:31 UTC
**Plan:** [202604/test\_suite\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202604/test_suite_speedup.md)

## Description

Measure, diagnose, and fix the parallel-tail bottleneck in tests/test_agent_launch_repeat.py via a sleep_between test seam. Target full-suite wall time ~50 s → ~15 s. See plans/202604/test_suite_speedup.md Phase 3.

## Notes

COMMIT: 8cb1e275

## Dependencies

- **Depends on:** [sase-l.2](sase-l.2.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`1927734`](https://github.com/sase-org/sase/commit/192773438e2a72cdcdb808672464f4ff7d1a6018) | feat: Zero the inter-spawn sleep in repeat-agent tests (sase-l.3) | [sase-l.3](sase-l.3.md) | 2026-04-24 01:07:34 |

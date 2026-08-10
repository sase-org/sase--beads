# Bead: sase-ib.2 — Eliminate idle waiting in ACE TUI tests

[Bead Pages](../README.md) / [sase-ib](README.md) / sase-ib.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wk/README.md) · **Assignee:** `sase-ib.2` · **Size:** large
**Created:** 2026-08-09 10:31:27 EDT · **Closed:** 2026-08-09 13:20:10 EDT
**Plan:** [202608/fast\_test\_suite\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_test_suite_1.md)

## Description

idle: replace the 20ms-granularity CPU-idle heuristic behind every `pilot.pause()` and every bounded waiter with event-driven barriers, so TUI tests stop spending over half their wall clock asleep.

## Notes

[2026-08-09T17:20:10Z · sase-ib.2] Implemented event-driven ACE TUI settle helpers, bounded waits, cost attribution, and fixed-sleep checker audit. Verified focused helper/wait/cost tests, former failure cluster, modal cost lane with zero CPU-idle labels, wait-helper checker, and just check static gates; broad full-suite tail exposed known flaky failure corroborated on sase-ct/sase-h8.

## Dependencies

- **Depends on:** [sase-ib.1](sase-ib.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.3](sase-ib.3.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.7](sase-ib.7.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ib.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ib.2.md) | [sase-ib.2](sase-ib.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cfe18d7`](https://github.com/sase-org/sase/commit/cfe18d7f0de46080e1a5b9e509845261e543b946) | perf(test): make ACE TUI waits event-driven | [sase-ib.2](sase-ib.2.md) | 2026-08-09 13:22:25 EDT |

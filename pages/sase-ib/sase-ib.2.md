# Bead: sase-ib.2 — Eliminate idle waiting in ACE TUI tests

[Bead Pages](../README.md) / [sase-ib](README.md) / sase-ib.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wk/README.md) · **Assignee:** `sase-ib.2` · **Size:** large
**Created:** 2026-08-09 10:31:27 EDT
**Plan:** [202608/fast\_test\_suite\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_test_suite_1.md)

## Description

idle: replace the 20ms-granularity CPU-idle heuristic behind every `pilot.pause()` and every bounded waiter with event-driven barriers, so TUI tests stop spending over half their wall clock asleep.

## Dependencies

- **Depends on:** [sase-ib.1](sase-ib.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.3](sase-ib.3.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.7](sase-ib.7.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ib.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ib.2/README.md) | [sase-ib.2](sase-ib.2.md) | 0 |

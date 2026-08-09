# Bead: sase-ib.1 — Suite cost harness and committed baseline

[Bead Pages](../README.md) / [sase-ib](README.md) / sase-ib.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wk/README.md) · **Assignee:** `sase-ib.1` · **Size:** medium
**Created:** 2026-08-09 10:30:56 EDT · **Closed:** 2026-08-09 11:20:04 EDT
**Plan:** [202608/fast\_test\_suite\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_test_suite_1.md)

## Description

baseline: build the per-cause suite cost harness (idle vs CPU, app boots, subprocess, parser, collection, worker RSS) on top of the existing timings store, and commit the measured starting numbers every later phase is scored against.

## Notes

[2026-08-09T15:20:04Z · sase-ib.1] Implemented opt-in test-cost harness, reporter, and committed baseline; verified focused cost tests, two consecutive just test-cost tests/test_test_cost.py runs, and final just check.

[2026-08-09T15:21:37Z · sase-ib.1] Verified focused cost/runner tests, just test-cost runs, final just check, and committed cost baseline harness changes

## Dependencies

- **Blocks:** [sase-ib.2](sase-ib.2.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.3](sase-ib.3.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.4](sase-ib.4.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.5](sase-ib.5.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.6](sase-ib.6.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ib.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ib.1/README.md) | [sase-ib.1](sase-ib.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b5b5ded`](https://github.com/sase-org/sase/commit/b5b5ded84d919cdd885938bbef4f896ae44a5634) | test: add suite cost attribution lane | [sase-ib.1](sase-ib.1.md) | 2026-08-09 11:23:25 EDT |

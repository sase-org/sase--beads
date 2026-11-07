# Bead: sase-1rq.2.1.3 — Make the test-cost lane finish inside its 180-minute timeout

[Bead Pages](../README.md) / [sase-1rq.2.1](sase-1rq.2.1.md) / sase-1rq.2.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) · **Assignee:** `sase-1rq.2.1.3` · **Size:** large
**Created:** 2026-11-07 10:24:47 EST
**Plan:** [202611/sase\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/sase_ci_green.md)

## Description

test-cost: CI Telemetry's test-cost job is cancelled at its unchanged 180-minute timeout, about 93% through 60,399 items on 3 workers (run 42347892210). Full CI's test (3.12) runs the same items on the same 3 workers in about 61 minutes, so the cost lane's own plugins (cost recorder plus --sase-detect-global-leaks / --sase-fail-on-global-leaks) add roughly 3x overhead. Find and remove that overhead. Then make the whole recipe pass: the run, test_cost_report, and check_test_cost_budgets. Change no timeouts, budgets, or leak gates.

## Dependencies

- **Blocks:** [sase-1rq.2.1.7](sase-1rq.2.1.7.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.3.md) | [sase-1rq.2.1.3](sase-1rq.2.1.3.md) | 0 |

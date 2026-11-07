# Bead: sase-1rq.3.1.1 — Make the install\_ui EarnedEta test hermetic to CARGO\_INCREMENTAL

[Bead Pages](../README.md) / [sase-1rq.3.1](sase-1rq.3.1.md) / sase-1rq.3.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.3.md) · **Assignee:** `sase-1rq.3.1.1` · **Size:** small
**Created:** 2026-11-07 08:10:11 EST
**Plan:** [202611/bob\_cli\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_cli_ci_green.md)

## Description

lint-incremental: fix the one deterministic lint-job failure. In the check-scripts step, EarnedEtaTests.test_seeded_history_shows_bar_range_plan_and_summary seeds history rows with incremental=True, but CI's rust-cache sets CARGO_INCREMENTAL=0, so no row matches and the "usually" ETA text never renders. Make the test independent of the caller's CARGO_INCREMENTAL, then prove it with and without the variable.

## Dependencies

- **Blocks:** [sase-1rq.3.1.4](sase-1rq.3.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3.1.1/README.md) | [sase-1rq.3.1.1](sase-1rq.3.1.1.md) | 0 |

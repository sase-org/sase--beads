# Bead: sase-gj.2 — Escalate on estimated serial runtime, not on the file-count ratio

[Bead Pages](../README.md) / [sase-gj](README.md) / sase-gj.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ue](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ue/README.md) · **Assignee:** `sase-gj.2` · **Size:** medium
**Created:** 2026-08-06 16:01:37 EDT · **Closed:** 2026-08-06 17:11:27 EDT
**Plan:** [202608/scoped\_lane\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202608/scoped_lane_latency.md)

## Description

budget: add a serial-runtime budget rule so a selection that would take longer than the governed full lane escalates, and keep the file-count ratio only as a fallback when no timing data exists.

## Notes

[2026-08-06T21:05:40Z · sase-gj.2] PROPOSED FOLLOW-UP: calibrate the duration table for parallel contention — per-test seconds recorded on the 28-worker full lane over-state a true serial run (measured 2026-08-06 on athena: 12 slow ACE files estimated 338.8s vs 298.2s actual serial, 1.14x; 11 selection-test files estimated 26.4s vs 11.8s actual, 2.2x), which biases RULE_SERIAL_BUDGET_EXCEEDED toward escalating early and is the likeliest cause of the replayed escalation rate rising from 6/17 to 13/17 commits.

[2026-08-06T21:05:57Z · sase-gj.2] PROPOSED FOLLOW-UP: the health store strips manifest["selected"] from selection records, so a later reader cannot recompute what a past scoped run was estimated to cost and compare it against the duration that run actually took — record the selection (or the estimate) on the record so the budget can be calibrated from real lane history instead of hand-run samples.

[2026-08-06T21:06:25Z · sase-gj.2] PROPOSED FOLLOW-UP: `just check` fails at the symvision gate on an unrelated pre-existing defect — three stale `--epic-symbol 'sase-gi.4(...)'` entries in the Justfile point at a closed bead ("Remove this stale --epic-symbol entry and clean up the symbol"). Blocks the lint gate for every agent in this repo until the entries and their symbols are cleaned up.

[2026-08-06T21:11:27Z · sase-gj.2] Serial-runtime budget rule (RULE_SERIAL_BUDGET_EXCEEDED) supersedes the file-count ratio wherever timing data exists; ratio kept as no-data fallback. Budget defaults to FULL_LANE_WALL_SECONDS (232s), configurable via SASE_TEST_SELECTION_MAX_SERIAL_SECONDS and tools/select_tests --max-serial-seconds; estimate computed on the candidate selection before discard, surfaced in --explain, the scoped one-line summary, and manifest schema 6 (max_serial_seconds). Verified: 141 selection/report/timings/tool tests pass, ruff + mypy clean, full suite 26380 passed / 7 skipped in 152s. just lint's symvision gate fails on a pre-existing unrelated stale --epic-symbol defect in the Justfile (recorded as a PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-gj.1](sase-gj.1.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gj.3](sase-gj.3.md) ◐ · ⧖ 2026-08-06
- **Blocks:** [sase-gj.7](sase-gj.7.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gj.2/README.md) | [sase-gj.2](sase-gj.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`af3aa32`](https://github.com/sase-org/sase/commit/af3aa326cfe5fa193251ed4968630a3a57fca731) | feat(test-selection): escalate on estimated serial runtime, not file count | [sase-gj.2](sase-gj.2.md) | 2026-08-06 17:14:32 EDT |

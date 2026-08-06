# Bead: sase-gj.7 — Land the scoped-lane latency epic

[Bead Pages](../README.md) / [sase-gj](README.md) / sase-gj.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ue](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ue/README.md) · **Assignee:** `sase-gj.7` · **Size:** small
**Created:** 2026-08-06 16:04:09 EDT · **Closed:** 2026-08-06 18:17:30 EDT
**Plan:** [202608/scoped\_lane\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202608/scoped_lane_latency.md)

## Description

land: re-measure the lane end to end against the real store, verify the combined tree, and state honestly which of the epic's numbers moved and which did not.

## Notes

[2026-08-06T22:16:49Z · sase-gj.7] PROPOSED FOLLOW-UP: FULL_LANE_WALL_SECONDS/SASE_TEST_SELECTION_MAX_SERIAL_SECONDS default (232s, set by the budget phase from a single 2026-08-06 measurement at 28 workers) may already be stale — a fresh timed `just test` during land on the same host the same day measured 159.0s pytest wall (161.9s total) with 26,497 passed/7 skipped, a larger suite finishing faster. Single-sample noise (host contention varies), so land is not changing the constant, but if this holds up across repeated measurements the budget/middle-gear crossover is currently looser than optimal and worth recalibrating.

[2026-08-06T22:17:30Z · sase-gj.7] Verified all six phases (timings/budget/gear/identity/tail/flakes) delivered in HEAD source (ca6c1e09e), not just their reports: per-input timings table + estimate_serial_seconds with explicit no-data reasons, RULE_SERIAL_BUDGET_EXCEEDED wired as an after-the-fact cost rule with MAX_RATIO retained as no-data fallback, the bounded non-blocking gear lease (try_acquire, released in run_pytest's finally, -n/SASE_PYTEST_WORKERS still rejected), the per-input environment fingerprint map with the nested sase_core_rs.abi3.so glob + content-hash fix, tail's p75/p90/max + slow_runs('scoped runs slower than the full lane') + width-grouped durations + honest 'cost not measured' for escalated runs, and flakes' reproducible_flake_nodeids (>=2 full runs, disjoint change sets) with flake-suppressed counted and shown separately from false negatives. One real gap found: docs/development.md's Selection Health section never documented tail's slow_runs counter or the cost-not-measured framing (tail's own commit cc241fae0 touched no docs) — fixed here with a new paragraph, reformatted via just fmt, fmt-md-check green. Re-measured end to end against the real host store: just selection-health (92 scoped/117 full-lane records) shows 43.5% escalated, median 37.3s / p75 171.4s / p90 435.4s / max 1372.6s scoped duration, 180,398 worker-seconds avoided, 6 false negatives (17 matches, all single-full-run occurrences correctly left uncorrelated) and 4 flake-suppressed (10 matches, correctly reproducing across disjoint full runs) per design; middle gear shows 0 leased/0 refused so far — every 'slower than the full lane' record still in the store predates budget/gear landing in that workspace (stale merge_base or schema<7), and no schema>=7 record has ever exceeded the serial budget, so both mechanisms are wired and unit/integration-tested but not yet exercised by a representative real selection. just selection-backtest --include-descendant-baseline over the last 50 commits: 19 with usable coverage ground truth, both closure-only and closure+contexts arms at 100% recall / 0 blind spots — recall did not regress; budget and gear changed only where tests run, never which. Timed just test: 26,497 passed / 7 skipped in 159.0s (161.9s total), faster than the 232s crossover the budget default is pinned to (flagged as a PROPOSED FOLLOW-UP, not changed here — single-sample noise). Restated savings honestly: charging today's 92 real records (escalated at 232s, else actual duration) gives ~12.5% saved vs an all-full baseline, below both the original day's 24% and the epic's 40-50% projection — because today's store is dominated by the epic's own self-referential test-selection-tooling churn (which unconditionally escalates via selection-tooling/justfile/root-conftest, not the new budget rule), not ordinary diff traffic; the projection assumed a representative sample this single-epic day did not provide, not that budget/gear are ineffective. just check-full green (exit 0: fmt/lint/keep-sorted/ruff/mypy/pyscripts/changelog/symvision/toobig/SASE validation/committed plans/full test suite all pass); just symvision re-run standalone also clean. Working tree carries one doc-only diff (docs/development.md); not committed, per this session's git-commit policy.

[2026-08-06T22:18:19Z · sase-gj.7] Re-verified land phase for epic sase-gj: all six sub-phases (timings, budget, gear, identity, tail, flakes) confirmed delivered in HEAD (ca6c1e09e) source; docs/development.md updated to document tail's slow_runs/'cost not measured' health fields (previously missing); just check-full and just symvision pass clean; just selection-backtest shows no recall regression.

## Dependencies

- **Depends on:** [sase-gj.2](sase-gj.2.md) ✓ · ⧖ 2026-08-06
- **Depends on:** [sase-gj.3](sase-gj.3.md) ✓ · ⧖ 2026-08-06
- **Depends on:** [sase-gj.4](sase-gj.4.md) ✓ · ⧖ 2026-08-06
- **Depends on:** [sase-gj.5](sase-gj.5.md) ✓ · ⧖ 2026-08-06
- **Depends on:** [sase-gj.6](sase-gj.6.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gj.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gj.7/README.md) | [sase-gj.7](sase-gj.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a042950`](https://github.com/sase-org/sase/commit/a04295008fbb1e7c973ffd9ed69b848d2cea7a68) | docs(test-selection): document the tail phase's slow-run and cost-not-measured fields | [sase-gj.7](sase-gj.7.md) | 2026-08-06 18:18:54 EDT |

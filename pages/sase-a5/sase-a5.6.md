# Bead: sase-a5.6 — Verify the speedup and guard it

[Bead Pages](../README.md) / [sase-a5](README.md) / sase-a5.6

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a5.6` · **Size:** small
**Created:** 2026-07-27 18:22:12 UTC · **Closed:** 2026-07-28 09:58:42 UTC
**Plan:** [202607/agents\_view\_hints\_perf.md](https://github.com/sase-org/sase--plans/blob/main/202607/agents_view_hints_perf.md)

## Description

verify: re-run the view-hints bench against the committed baseline, record the after numbers, add a regression floor, and sync the help popup and perf runbook with any user-visible behavior change.

## Notes

[2026-07-28T09:58:26Z · sase-a5.6] Implemented a view-hints regression-floor checker with unit tests, added just/CI wiring, ignored the runtime report, and synced the perf runbook, help popup, and changelog for capped hint scans. Verification: just install; pytest tests/perf/test_view_hints_regression.py passed; just view-hints-perf-check --runs 3 passed with agents.view_files p50 large first 1.558 ms vs 30.949 ms baseline, repeat 1.640 ms vs 20.905 ms, unfolded family 2.694 ms vs 85.402 ms, repeat/refresh annotated_chars 0 vs 102541 baseline, unfolded family annotated_chars 128016 vs 614538 baseline; explicit pytest -s -m slow tests/perf/bench_tui_trace.py::test_view_hints_scenario passed. Lowered-threshold soak wrote 20 watchdog entries, but parsed stacks had no hint-path frames. just check passed fmt/ruff/mypy/pyscripts/symvision/toobig but failed SASE validation because the configured provider beads sidecar is missing and git@github.com:sase-org/sase--beads.git was not accessible; validate-committed-plans passed. just test produced 22847 passed/7 skipped with 9 unrelated xdist failures; the exact failures passed serially and with -n 5.

## Dependencies

- **Depends on:** [sase-a5.5](sase-a5.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a5.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a5.6/README.md) | [sase-a5.6](sase-a5.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a49e63e`](https://github.com/sase-org/sase/commit/a49e63e3581075d5681a3a593234ddb6462f78d1) | perf(ace): guard Agents-tab view-hints latency (sase-a5.6) | [sase-a5.6](sase-a5.6.md) | 2026-07-28 10:01:15 |

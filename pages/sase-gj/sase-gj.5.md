# Bead: sase-gj.5 — Report the scoped lane's tail, not just its median

[Bead Pages](../README.md) / [sase-gj](README.md) / sase-gj.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ue](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ue/README.md) · **Assignee:** `sase-gj.5` · **Size:** small
**Created:** 2026-08-06 16:03:17 EDT · **Closed:** 2026-08-06 16:21:03 EDT
**Plan:** [202608/scoped\_lane\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202608/scoped_lane_latency.md)

## Description

tail: add duration percentiles and a "slower than the full lane" counter to `just selection-health` so a latency regression is visible in the project's own health metric.

## Notes

[2026-08-06T20:21:03Z · sase-gj.5] Added p75/p90/max scoped-duration percentiles, a FULL_LANE_WALL_SECONDS=232.0s constant, and the slow_runs latency-regression counter (scoped runs slower than the full lane, with selected-file count and rules, escalated runs called out separately as 'cost not measured') to SelectionHealth/summarize/render_report/health_payload in tests/_test_selection_health.py and tests/_test_selection_health_report.py, plus new tests in tests/test_test_selection_health_report.py. Verified: just test tests/test_test_selection_health_report.py (14 passed) and just check (all lint gates + scoped test lane) both pass clean; ran just fmt to fix one formatting issue found by just check.

## Dependencies

- **Blocks:** [sase-gj.7](sase-gj.7.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gj.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gj.5/README.md) | [sase-gj.5](sase-gj.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cc241fa`](https://github.com/sase-org/sase/commit/cc241fae0c5cb96e0dbffc468e1cc5f77fde4d6b) | feat(test-selection): report the scoped lane's tail, not just its median | [sase-gj.5](sase-gj.5.md) | 2026-08-06 16:22:21 EDT |

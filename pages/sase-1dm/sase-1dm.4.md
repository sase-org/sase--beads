# Bead: sase-1dm.4 — Stage, backtest, and pressure sections in the stats report

[Bead Pages](../README.md) / [sase-1dm](README.md) / sase-1dm.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u4.md) · **Assignee:** `sase-1dm.4` · **Size:** medium
**Created:** 2026-09-30 16:20:10 EDT · **Closed:** 2026-09-30 18:07:07 EDT
**Plan:** [202609/tool\_stats\_demand.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_stats_demand.md)

## Description

core-stats-detail: in sase-core, extend the stats report with per-stage distributions, whole-run and per-stage chronological backtests, and a bucketed host-pressure section read from the stages and samples tables.

## Notes

[2026-09-30T22:07:07Z · sase-1dm.4] core-stats-detail done in sase-core working tree (uncommitted, host finalizer commits): per-stage distributions (runs/ok/failed/incomplete, finished p50/p90, p90_over_p50, total_hours, median_offset_ms, recipe-ordered), whole-run + per-description chronological backtests (20-min-priors, 60-prior p10/p90 bands, width hi/max(lo,1000ms), meets_target), and report-level 30s-bucket host-pressure section (busy buckets, memory>10 PSI shares, PSI/load p90s) loaded from stages/samples tables with newest-first caps. Verified: just check gate green (fmt, clippy -D warnings, all tests incl. 7 new stats + 1 store end-to-end tests); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1dm.3](sase-1dm.3.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dm.5](sase-1dm.5.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dm.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dm.4/README.md) | [sase-1dm.4](sase-1dm.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b381879`](https://github.com/sase-org/sase-core/commit/b381879ebb19d255b8519e7a89ad983b799040d0) | feat(tool-run): add stage, backtest, and pressure sections to stats report | [sase-1dm.4](sase-1dm.4.md) | 2026-09-30 18:09:47 EDT |

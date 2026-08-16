# Bead: sase-mj.2 — Python perf facade and view model

[Bead Pages](../README.md) / [sase-mj](README.md) / sase-mj.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.032](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.032.md) · **Assignee:** `sase-mj.2` · **Size:** medium
**Created:** 2026-08-15 20:25:54 EDT · **Closed:** 2026-08-15 21:43:42 EDT
**Plan:** [202608/statistics\_perf\_view.md](https://github.com/sase-org/sase--plans/blob/main/202608/statistics_perf_view.md)

## Description

stats_facade: add the thin `sase.stats` adapter that calls the new Rust binding, fans out the fixed telemetry-store query set, and builds one immutable presentation-ready PerfView with status grading and coverage notes.

## Notes

[2026-08-16T01:43:04Z · sase-mj.2] PROPOSED FOLLOW-UP: just check symvision fails on pre-existing private cross-file imports in models_panel_provider_* and _now helpers (vcs_log/bead/prompt) — sase-mj.2 did not touch those files; other just check lint gates and the escalated full pytest suite passed.

[2026-08-16T01:43:42Z · sase-mj.2] Added thin sase.stats.perf_query adapters (perf_logs_query + fixed telemetry fan-out) and I/O-free build_perf_view with status grading, deltas, and coverage notes. load_statistics_view builds PerfView only when view==perf. Verified just install, ruff/mypy, 21 new facade tests, and escalated full pytest (30635 passed, 10 skipped). just check otherwise green except a pre-existing unrelated symvision private-import failure noted as follow-up.

[2026-08-16T01:44:47Z · sase-mj.2] Added thin sase.stats.perf_query adapters (perf_logs_query + fixed telemetry fan-out) and I/O-free build_perf_view with status grading, deltas, and coverage notes. load_statistics_view builds PerfView only when view==perf. Verified just install, ruff/mypy, 21 new facade tests, and escalated full pytest (30635 passed, 10 skipped). just check otherwise green except a pre-existing unrelated symvision private-import failure noted as follow-up.

## Dependencies

- **Depends on:** [sase-mj.1](sase-mj.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mj.3](sase-mj.3.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mj.2/README.md) | [sase-mj.2](sase-mj.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a244947`](https://github.com/sase-org/sase/commit/a244947a8cc040ddaba013c39a4807bc07dd8cf7) | feat(stats): add Python perf facade and immutable PerfView | [sase-mj.2](sase-mj.2.md) | 2026-08-15 21:45:47 EDT |

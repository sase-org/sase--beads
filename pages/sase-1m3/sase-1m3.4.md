# Bead: sase-1m3.4 — sase-core project\_stats wire, git history walk, cache, and footer attribution

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.4` · **Size:** large
**Created:** 2026-10-16 22:05:22 EDT · **Closed:** 2026-10-17 02:47:51 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

core-engine: add `sase_core::project_stats` with the full request/response wire, a hardened git runner, the cached incremental history walk, the Output and lifetime aggregates with footer attribution, per-facet seams, and the `project_stats_query` binding.

## Notes

[2026-10-17T02:11:49Z · sase-1m3.4] PROPOSED FOLLOW-UP: Stats attribution decision record deferred — the parent epic selected stats_decision_record=no; no decisions-web record or other memory edit is authorized for this phase.

[2026-10-17T07:01:31Z · sase-1m3.4.1.land] Child epic sase-1m3.4.1 is closed. Core-engine scope is complete: request/response wire, hardened git runner, cached full-DAG history with footer attribution, Output/lifetime aggregation, facet seams, and project_stats_query binding.

Integrated verification: domain, binding, and file_history runner tests passed after landing repairs (identity vs history union, nullable unavailable counts, facade split, PROJECT_STATS_SASE_REPO acceptance, equal-tip persist skip and outcome intern). Actual sase measurement on this checkout: 16215 lifetime commits, 1865 range commits, tip 315092afebe542524e37d6b69c27030b77e02c2d, cold 1473.0 ms, warm median 134.8 ms, budget 30s/32MiB, no extension startup. Combined history/directory/plans target was not claimed.

Guarded sase tool run check 31b152b8a1c739389915263e812608ea stopped on clean-base clippy::nonminimal_bool in project_onboarding/classify.rs:500-502 (unchanged since 98c3682f, identical at HEAD be2bfbee), tracked by sase-1an. Not remaining core-engine work. Legacy file_history batch deadlock remains sase-1mb. Parent skipped decision record stays skipped (stats_decision_record=no). epic-symbols sase-1m3.4: none. Leave ancestor epic sase-1m3 and plan:202610/sase_stats_project.md open.

## Dependencies

- **Blocks:** [sase-1m3.5](sase-1m3.5.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1m3.6](sase-1m3.6.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1m3.7](sase-1m3.7.md) ◐ · ⧖ 2026-10-16
- **Blocks:** [sase-1m3.8](sase-1m3.8.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.4.md) | [sase-1m3.4](sase-1m3.4.md) | 0 |

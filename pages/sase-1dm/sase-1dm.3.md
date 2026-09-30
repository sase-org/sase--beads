# Bead: sase-1dm.3 — Rust stats report over the runs table

[Bead Pages](../README.md) / [sase-1dm](README.md) / sase-1dm.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u4.md) · **Assignee:** `sase-1dm.3` · **Size:** medium
**Created:** 2026-09-30 16:20:08 EDT · **Closed:** 2026-09-30 17:29:29 EDT
**Plan:** [202609/tool\_stats\_demand.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_stats_demand.md)

## Description

core-stats: in sase-core, add the read-only tool_run_stats_report function and binding covering outcomes, durations, routes, ceiling kills, waste, reruns, providers, trend, repeats, duplicates, and demand aggregates.

## Notes

[2026-09-30T21:29:07Z · sase-1dm.3] PROPOSED FOLLOW-UP: sase_gateway sudo_runner dispatch test failed once under the full parallel check with ETXTBSY invoking sudo, then passed in isolation (46/46) and on a full-check rerun; consider filing a sase-core flake bead

[2026-09-30T21:29:29Z · sase-1dm.3] core-stats done in sase-core (uncommitted working tree): tool_run_stats_report + tool_run_stats_report binding cover outcomes, durations, routes, ceiling kills, waste, reruns, providers, trend, repeats, duplicates, demand aggregates. Verified: 18 stats unit + 4 store tests (incl. unmigrated store, days bounds, missing store) + 1 binding round-trip pass; just fmt/fast clean; sase tool run check green in sase-core checkout (first run hit an unrelated sudo_runner ETXTBSY load flake, green on rerun; filed as PROPOSED FOLLOW-UP). No commit per host-owned completion; sase-1dm.4 builds on these files.

## Dependencies

- **Depends on:** [sase-1dm.1](sase-1dm.1.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dm.4](sase-1dm.4.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dm.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dm.3/README.md) | [sase-1dm.3](sase-1dm.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6e23783`](https://github.com/sase-org/sase-core/commit/6e23783d04da778b3be1d5ae6fc3b3e81cf1c830) | feat(tool-run): implement core-stats report for sase-1dm.3 | [sase-1dm.3](sase-1dm.3.md) | 2026-09-30 17:31:36 EDT |

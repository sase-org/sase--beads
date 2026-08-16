# Bead: sase-n7.2 — Kill the N+1 proc-store reads

[Bead Pages](../README.md) / [sase-n7](README.md) / sase-n7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03q](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03q.md) · **Assignee:** `sase-n7.2` · **Size:** medium
**Created:** 2026-08-16 11:16:45 EDT · **Closed:** 2026-08-16 11:59:05 EDT
**Plan:** [202608/tui\_startup\_monitor\_reconcile.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_startup_monitor_reconcile.md)

## Description

snapshot: add a snapshot-scoped proc lookup so `get_proc` stops re-reading and re-parsing the whole store per id, thread one snapshot through the reconcile pass and `_with_proc_projection`, and test that proc-store reads stay bounded regardless of record count.

## Notes

[2026-08-16T15:57:29Z · sase-n7.2] PROPOSED FOLLOW-UP: test_load_config_layers_overlay_detected flakes under xdist — just check escalated to the full suite (core-identity-changed) and failed once with overlay:sase_athena.yml vs overlay:sase_extra.yml; the same test passes in isolation and is unrelated to the proc-store snapshot change.

[2026-08-16T15:58:09Z · sase-n7.2] PROPOSED FOLLOW-UP: lane helpers still re-read the proc store per candidate — active_monitor_for_lane and monitor_blocking_start_for_lane call should_reconcile_dead_supervisor without a shared snapshot; CLI start/inspect path, not TUI list.

[2026-08-16T15:59:05Z · sase-n7.2] Added read_proc_snapshot and snapshot-scoped get_proc; threaded one snapshot through reconcile_dead_supervisors_for_records and list_monitors/_with_proc_projection (no module-level cache). Verified: get_proc snapshot lookups do not re-invoke read_procs_snapshot; one reconcile_dead_supervisors pass over 8 running records performs exactly one proc-store read; list_monitors proc-store reads stay at 2 for 3 and 12 records; monitor store/reconcile/proc-facade and procs facade suites green; just check lint gates passed. Escalated scoped run executed the full suite (31096 passed); the single failure was the unrelated xdist flake noted above.

[2026-08-16T16:01:08Z · sase-n7.2] Added read_proc_snapshot and snapshot-scoped get_proc; threaded one snapshot through reconcile_dead_supervisors_for_records and list_monitors/_with_proc_projection (no module-level cache). Verified: get_proc snapshot lookups do not re-invoke read_procs_snapshot; one reconcile_dead_supervisors pass over 8 running records performs exactly one proc-store read; list_monitors proc-store reads stay at 2 for 3 and 12 records; monitor store/reconcile/proc-facade and procs facade suites green; just check lint gates passed.

## Dependencies

- **Blocks:** [sase-n7.4](sase-n7.4.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n7.2/README.md) | [sase-n7.2](sase-n7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3f3f61d`](https://github.com/sase-org/sase/commit/3f3f61d14d9a53441fae2d98b92ce4882c929147) | perf(monitor): resolve many proc ids from one store snapshot | [sase-n7.2](sase-n7.2.md) | 2026-08-16 12:04:13 EDT |

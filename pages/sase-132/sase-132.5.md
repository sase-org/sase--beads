# Bead: sase-132.5 — Attribute and fix the doubled axe surface startup cost

[Bead Pages](../README.md) / [sase-132](README.md) / sase-132.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0n7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0n7.md) · **Assignee:** `sase-132.5` · **Size:** medium
**Created:** 2026-09-18 15:22:37 EDT · **Closed:** 2026-09-18 17:29:03 EDT
**Plan:** [202609/tui\_startup\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_startup_regression.md)

## Description

axe-ready: using the axe spans added in baseline, attribute why axe_ready_seconds doubled (2.0 s to 3.5 s median, step on 2026-08-27/28) and restore it to about 2 s, keeping the axe first load off the visible surface's critical path.

## Notes

[2026-09-18T21:27:03Z · sase-132.5] Attribution (sase-132.1 traces + tui_startup.jsonl): axe_ready stepped 2.33s (08-26) to 4.42s (08-27) while pre-mount/first-paint barely moved. Live traces at SHA 0320daed showed axe.collect 1.3-2.9s with include_full_snapshots=true, file_opens=452, run_json_parses=402, run_index_reads=40 even when initial_tab=agents. Root cause: _axe_collector_kwargs forced a full chop-history walk on first load (first_load_pending), so startup decoded ~40 chops x ~10 runs while the Agents tab was showing. Standalone full collect is ~110ms; in-app it inflated 10-20x under agents-load contention.

[2026-09-18T21:27:31Z · sase-132.5] Fix: startup first load is header-only (include_full_snapshots=False); pending first load no longer forces full snapshots. When the AXE tab is the visible surface, a coalesced _schedule_axe_async_refresh completes snapshots in the background after the cheap paint. Other tabs warm on tab switch / auto-refresh (existing watch_current_tab path). Tests: file_opens==0 on a 40-chop x 10-run fixture; kwargs first-load off-tab is header-only; axe/agents startup workers do not gate each other.

[2026-09-18T21:27:58Z · sase-132.5] After: 10 traced live startups on athena host_state=busy (load1~24) stored at ~/.sase/perf/sase-132.5_live_busy-20260918T212208Z (index ~/.sase/perf/sase-132.5_capture_index.json). axe_ready median 2.20s (min 1.59 max 2.78); all 10 startup axe.collect spans have file_opens=0 and include_full_snapshots=false; axe.startup 199-737ms vs 1460-3167ms baseline. Collect bench ~/.sase/perf/sase-132.5_axe_collect_bench.json: header file_opens=0. Remaining 0.20s vs the 2.0s target on this busy host is pre-mount 1.19s median + first-paint 0.57s median (sase-132.4 / sase-132.6), not the axe collector.

[2026-09-18T21:28:26Z · sase-132.5] PROPOSED FOLLOW-UP: Recapture axe_ready median after premount-diet and first-paint land, preferably host_state=quiet — 10 busy-host sessions at this SHA are 2.20s median with file_opens=0; the leftover 0.20s is process_start_to_on_mount 1.19s + on_mount_to_first_paint 0.57s, owned by sase-132.4/sase-132.6, not a further axe-history walk.

[2026-09-18T21:29:03Z · sase-132.5] Verified: startup axe first load is header-only (include_full_snapshots=false, file_opens=0) on 10/10 busy-host live traces (~/.sase/perf/sase-132.5_live_busy-20260918T212208Z); axe.startup 199-737ms vs 1.5-3.2s baseline. axe_ready median 2.20s (min 1.59 max 2.78) at load1~24 — leftover 0.20s is pre-mount 1.19s + first-paint 0.57s (sase-132.4/132.6), not chop-history I/O. Tests: 40x10 chop fixture file_opens==0, first-load kwargs skip full snapshots, axe/agents workers do not gate each other. epic-symbols: none leftover.

## Dependencies

- **Depends on:** [sase-132.1](sase-132.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-132.7](sase-132.7.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-132.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-132.5/README.md) | [sase-132.5](sase-132.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`85fef14`](https://github.com/sase-org/sase/commit/85fef143a06f8f25965662998d67c1d690edc7fa) | perf(ace): skip chop-history walk on axe startup first load | [sase-132.5](sase-132.5.md) | 2026-09-18 17:31:15 EDT |

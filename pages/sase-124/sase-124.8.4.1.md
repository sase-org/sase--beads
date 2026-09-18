# Bead: sase-124.8.4.1 — Capture and attribute the missing live freshness evidence

[Bead Pages](../README.md) / [sase-124.8.4](sase-124.8.4.md) / sase-124.8.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-124.8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-124.8.land.md) · **Assignee:** `sase-124.8.4.1` · **Size:** medium
**Created:** 2026-09-17 22:34:32 EDT · **Closed:** 2026-09-18 00:16:54 EDT
**Plan:** [202609/complete\_agents\_freshness\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/complete_agents_freshness_acceptance.md)

## Description

controlled-acceptance: gather the required busy, idle, marker, capacity, stall, and navigation measurements and attribute every target.

## Notes

[2026-09-18T04:14:05Z · sase-124.8.4.1--2] EVIDENCE: Controlled acceptance capture completed at commit f90c6b549f6e415e60c1d97581f073acbeade923 in /home/bryan/.sase/perf/sase-124.8.4.1-live-20260918T025836Z; explicit summaries file:explicit:f5f58a0ec40e12dd1aa9bebc and file:explicit:144230fdd9b2d38483af7ac9. Busy window 1800.81s with 90 scripted j/k; idle candidate 600.393s with 0 scripted input but classified missed_busy_host (load1 avg 17.115, max 22.938, 23.15 agent runners avg). refresh.auto_tick 240 samples p50/p95/max 114.625/2832.157/12043.693 ms, 38 ticks >2s; attention 203 cache + 36 network polls, 0 errors, slow ticks mostly AXE/notifications/agents reloads and load/disk/prompt costs, not attention waits. Agents key-to-paint: next 44 samples p50/p95/max 24.396/88.893/200.187 ms; prev 45 samples 24.976/81.313/763.471 ms. Watchdog rows: 208 total, duration p50/p95/max 782/2081/2215 ms. Loader slow rows: 87; auto_refresh:full disk p95 2277.401 ms, prep p95 1659.089 ms; tier1_index_revalidate disk max 9545.967 ms. Capacity evidence preserved from predecessor: file:explicit:7149138b09eabe6ff5ba5226 plus 95 focused tests showed hidden capacity 2/2, stale capacity off-thread, attention modes [true,false], and local Agents refresh before blocked cache release. Marker targets remain unverified because sase-zr.7.1/.2/.3/.5 were still in_progress before capture.

[2026-09-18T04:14:37Z · sase-124.8.4.1--2] PROPOSED FOLLOW-UP: AXE cached j/k exceeds the 16 ms p95 budget - bench_tui_jk_pytest in /home/bryan/.sase/perf/sase-124.8.4.1-live-20260918T025836Z/bench_tui_jk_pytest.log failed test_bench_axe_jk with next p50/p95/max 14.035/29.416/34.937 ms and prev 10.781/13.627/14.337 ms; no matching open bead found by search for "AXE cached" or "AXE j/k".

[2026-09-18T04:15:09Z · sase-124.8.4.1--2] PROPOSED FOLLOW-UP: Fleet fault j/k paths exceed the 16 ms p95 budget under loaded acceptance capture - bench_tui_jk_pytest failed hung_host next/prev p95 33.497/26.806 ms, reconnect_churn 18.994/20.827 ms, and event_burst 33.754/34.480 ms, with max values up to 431.167 ms; preserve sase-127.3 genuine-change/forced-source behavior while attributing the repaint/refresh path.

[2026-09-18T04:15:39Z · sase-124.8.4.1--2] PROPOSED FOLLOW-UP: bench_tui_trace startup can fail to settle under loaded host conditions - /home/bryan/.sase/perf/sase-124.8.4.1-live-20260918T025836Z/bench_tui_trace_script.log exited 1 after event-loop and pump stalls up to 41s and AssertionError("ACE benchmark startup did not settle within 20s"); classify benchmark robustness versus startup regression before relying on this bench as green evidence.

[2026-09-18T04:16:11Z · sase-124.8.4.1--2] PROPOSED FOLLOW-UP: just check current-tree scoped lane has independent Commits/Stitches regressions - /home/bryan/.sase/perf/sase-124.8.4.1-live-20260918T025836Z/just_check.log failed test_sidecar_filter_and_compatibility_toggle_share_collection_scope (selection changed from ccccc... to aaaaa... after toggling sidecar filter) and test_commits_renderer_builds_compact_single_line_rows (option_count 4, expected 3). Existing tracking found for selected-tribe p95 (sase-lx) and empty-home git identity (sase-120), so those are not proposed here.

[2026-09-18T04:16:54Z · sase-124.8.4.1--2] Verified controlled-acceptance capture at f90c6b549f6e415e60c1d97581f073acbeade923 with live run /home/bryan/.sase/perf/sase-124.8.4.1-live-20260918T025836Z and summary artifacts file:explicit:f5f58a0ec40e12dd1aa9bebc / file:explicit:144230fdd9b2d38483af7ac9. Captured 30m busy window, classified 10m idle candidate as missed_busy_host, attributed refresh ticks/key-to-paint/attention/load/stall data, preserved deterministic capacity evidence, recorded marker targets as unverified because sase-zr.7.* marker work was still in_progress, and appended PROPOSED FOLLOW-UP notes for AXE, Fleet, bench_tui_trace startup, and independent just-check Commits/Stitches failures. epic-symbols reported none.

## Dependencies

- **Blocks:** [sase-124.8.4.2](sase-124.8.4.2.md) ✓ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.8.4.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-124.8.4.1.md) | [sase-124.8.4.1](sase-124.8.4.1.md) | 0 |

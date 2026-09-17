# Bead: sase-124.7 — Before/after verification on athena and regression coverage

[Bead Pages](../README.md) / [sase-124](README.md) / sase-124.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mc.md) · **Assignee:** `sase-124.7` · **Size:** medium
**Created:** 2026-09-17 10:59:47 EDT · **Closed:** 2026-09-17 16:59:39 EDT
**Plan:** [202609/agents\_tab\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_freshness.md)

## Description

verify: capture before/after trace, perf, and stall data on athena against the acceptance targets, run the benches, and record results on the epic bead.

## Notes

[2026-09-17T20:58:00Z · sase-124.7] PROPOSED FOLLOW-UP: Live athena still performs broad slow loads — 2026-09-17 16:02 EDT last-30m window had 32 tui_agent_load_slow rows, 28 full loads, 18 auto_refresh full loads, max disk 29.996 s, latest auto_refresh full disk 3.569 s; the idle-host zero-full-load target is not met.

[2026-09-17T20:58:06Z · sase-124.7] PROPOSED FOLLOW-UP: Agents-tab hitches remain outside the fixed unread/countdown paths — last-30m live stall log had 42 agents-tab hitch/stall rows, max 3.111 s, with stacks pointing at runtime row patching/live-hint row patch/fleet projection paths.

[2026-09-17T20:58:51Z · sase-124.7] PROPOSED FOLLOW-UP: j/k regression floors fail under loaded athena — just test-slow tests/ace/tui/bench_tui_jk.py ended 5 failed / 5 passed: AXE next/prev p95 34.45/23.06 ms, selected-tribe fold1 next/prev p95 54.03/43.91 ms, and Fleet hung_host/reconnect_churn/event_burst p95 roughly 27-33 ms against the 16 ms floor.

[2026-09-17T20:58:54Z · sase-124.7] PROPOSED FOLLOW-UP: Live auto-tick trace coverage was stale during final acceptance — active TUI had no refresh.auto_tick rows in the last 30 minutes; latest trace row was 2026-09-17T15:05:53-0400, and the last 200 stale refresh.auto_tick rows still showed p50 2509 ms, p95 6867 ms, max 11544 ms.

[2026-09-17T20:59:39Z · sase-124.7] Verified on athena at 739caf01ff: trace bench passed (5 tests in 492.58s); real-archive load-tiering bench wrote ~/.sase/perf/agent_load_tiering_sase-124.7_athena_real_20260917.json with production_bounded p50/p95 1421/1693 ms, production_full_history 2232/2561 ms, unchanged refresh 249/952 ms; fixed unrelated stale Symvision epic-symbol by re-keying render_svg_to_png to open sase-123.4; just _lint-symvision passed; just check passed after scoped tests escalated to the full suite. Live athena acceptance remains mixed: slow full loads, Agents hitches, stale trace coverage, and j/k bench failures were recorded as PROPOSED FOLLOW-UP notes on this phase; no sase-124.7 epic-symbol entries remained before close.

## Dependencies

- **Depends on:** [sase-124.1](sase-124.1.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-124.2](sase-124.2.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-124.3](sase-124.3.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-124.4](sase-124.4.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-124.5](sase-124.5.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-124.6](sase-124.6.md) ✓ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.7/README.md) | [sase-124.7](sase-124.7.md) | 0 |

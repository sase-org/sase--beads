# Bead: sase-1nf.14.1 — Reduce measured TUI GC producers and verify both hosts

[Bead Pages](../README.md) / [sase-1nf.14](sase-1nf.14.md) / sase-1nf.14.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.14](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.md) · **Assignee:** `sase-1nf.14.1.land`
**Created:** 2026-10-24 13:37:43 EDT · **Closed:** 2026-10-30 02:37:12 EDT
**Plan:** [202610/measured\_tui\_gc\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/measured_tui_gc_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/measured_tui_gc_fixes.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:cc1fcd3f9d4bd944a9c454b5 | attached via sase artifact create --bead |

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/measured_tui_gc_fixes.md

<!-- sase:links:end -->

## Description

Reduce graph and render churn and retained UI caches, preserve quiet-time memory backstops, and establish the GC and navigation targets on restarted Athena and Apollo TUIs.

## Notes

[2026-10-30T03:06:22Z · sase-1nf.14.1.land] LAND TRIAGE (sase-1nf.14.1.land, 2026-10-29). Verification: phases .1 (0189f13f7b), .2 (3d70e0a81b, 98668bf431), .4 (0d11a115db), .5 (720b2a22bc), and .6 (353d833bf0) landed as reported. Phase .3 graph-allocation NEVER landed: its agent crashed after the close and a lease reset discarded its changes (crash chain since fixed by 9012f46cf9). The recovered diff is file:explicit:cc1fcd3f9d4bd944a9c454b5. .7/.8 closed on a user-confirmed FAIL/INCOMPLETE matrix (gates 6faea19e, 4cadd2a2) for source 196690f6cb, which LACKED the graph fix. Remaining epic work goes to a closeout tale: re-land graph-allocation, and fix the reporter's absolute 302 s heartbeat cap. That cap came from .1's HEARTBEAT_MAX_GAP_S and rejects delayed but fully accounted heartbeats (.7 PROPOSED FOLLOW-UP #2). FOLLOW-UP OUTCOMES: (1) .2 #1, inline ToolRun cannot be adopted by monitor -J: filed new task sase-1pv (large, ready; related sase-1di, sase-17g). (2) .7 #1 and .8 #4, fixed code misses idle-GC p95/GC share/hitch share/swap: not caused by this epic (pre-existing r5 failures; uncontrolled comparison). Corroborated existing sase-1nc with +1. (3) .8 #3, a new preflighted 24 h interval: duplicate of sase-1f3, corroborated with +1. The user declined further waiting on this epic, so no new capture is planned here. (4) .8 #5, soak_wait matched PID instead of app_instance_id: that script lived outside the repo. Declined as a task; instead the tale adds one runbook sentence saying exec restarts keep PID, start ticks, and boot ID. INTEGRATION: 212a476786 occupancy fields are in agent_render_key (compatible with .4's skip). b4d59ac50e's <3.14 census skip is compatible with .6. f843bd8100 and 8d41b72218 changed capacity loading/copy paths, so the tale re-audits the recovered classifier against them.

[2026-10-30T06:37:12Z · sase-1nf.14.1.land--2] Closeout tale verified. Producer/policy phases landed as reported: .1 (0189f13f7b), .2 (3d70e0a81b, 98668bf431), .4 (0d11a115db), .5 (720b2a22bc), .6 (353d833bf0). .3 graph-allocation re-landed here from file:explicit:cc1fcd3f9d4bd944a9c454b5: CachedGraphNeeds/classify_cached_graph_needs/own_required_apply_snapshot in _loading_graph.py wired to worker/apply/merge paths. Capacity-path audit clean: f843bd8100 runner refresh stays on worker-owned prep.filtered_agents/estimate copies plus capacity_agents, 8d41b72218 uses copy_agent_rows_relinked, 212a476786 capacity fields via worker paths, named-proc carryover/dismissed/relationship rebuild/fleet projection all on detached copies, fleet always copied when present. Tests: test_agents_tab_graph_isolation.py incl new test_authoritative_with_capacity_report_leaves_cached_history_untouched plus test_tui_freeze_report_acceptance.py/activity.py (40 passed), plus test_agent_graph_copy.py (49 passed with isolation+freeze), plus capacity closure suites (54 passed); symvision clean; git diff --check clean; no PNG goldens moved. Benchmark file:explicit:d0e2fb9ef3c7f133be198c25: 1000-row authoritative 1002->0 clones, tracemalloc peak ~11.2MB->~3.1MB, ~994ms->~683ms; no claim all graph garbage gone. Heartbeat fix heartbeat_delay=accept: HEARTBEAT_MISSING_GAP_S=1.5*interval replaces 302s cap, window_s/uptime agreement kept as continuity witness, delayed_interval_count in text+JSON, activity reporter shares bound; runbook sentence added that exec restarts keep PID/start-ticks/boot-ID so watchers must key on app_instance_id. Check: sase tool run check 34889e9ad09857b1e454bc38e9c23871 timed out 1h and 99cc95deba3cffd9af1f1ae41fd4c34f timed out 1.5h, both incomplete in test(scoped) after every lint/SASE-validation/docs stage passed; focused suites above green on this tree. Acceptance NOT met: fixed source 196690f6cb (without graph-allocation) measured FAIL/INCOMPLETE on both hosts: idle full-GC p95 4.476/1.051s, GC share 12.60%/4.28%, hitch share 15.29%/0.71%, Athena VmSwap max 631345152B, no four-hour/busy-hour/24h coverage; user closed .7/.8 on that matrix (gates 6faea19e, 4cadd2a2). Refs research:202610/tui_gc_fixed_capture_20261028.md and research:202610/tui_gc_fixed_soak_20261029.md. Follow-ups: sase-1pv new; sase-1nc and sase-1f3 corroborated; soak_wait PID pinning declined as task, handled by runbook sentence.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.14.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.1.land.md) | [sase-1nf.14.1](sase-1nf.14.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3266724`](https://github.com/sase-org/sase/commit/3266724c91a3e59aeab0b2969952c8adcdaac379) | feat(tui-gc): re-land graph-allocation classifier and accept delayed heartbeats | [sase-1nf.14.1](sase-1nf.14.1.md) | 2026-10-30 02:40:29 EDT |
| sase--plans | [`sase--plans@6a90aaf`](https://github.com/sase-org/sase--plans/commit/6a90aafbb6d1a5e4767aae046bce8049f9c16f9d) | chore(plans): mark measured\_tui\_gc\_closeout tale done | [sase-1nf.14.1](sase-1nf.14.1.md) | 2026-10-30 02:46:05 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.14.1.1][1] | Need the epic decisions and design context for this phase | 1 |
| read-by | [agent:sase-1nf.14.1.2][2] | epic decisions | 2 |
| read-by | [agent:sase-1nf.14.1.4][3] | parent epic scope and decisions | 1 |
| read-by | [agent:sase-1nf.14.1.5--2][4] | Need epic decisions governing this phase | 1 |
| read-by | [agent:sase-1nf.14.1.7--1][5] | Need final epic decisions and current closure obligations | 1 |
| read-by | [agent:sase-1nf.14.1.land--2][6] | closeout needs parent status for close note | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.14.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.14.1.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.14.1.4/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.1.5.md
[5]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.1.7.md
[6]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.1.land.md

<!-- sase:referenced-by:end -->

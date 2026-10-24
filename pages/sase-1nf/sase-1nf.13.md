# Bead: sase-1nf.13 — Measure and attribute the TUI GC freezes on restarted TUIs

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.13

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.13` · **Size:** medium
**Created:** 2026-10-20 13:36:16 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:0a6685051ab0553815b6d538 | attached via sase artifact create --bead |
| related | file:explicit:0e0e91825f3fb985c3a2a953 | attached via sase artifact create --bead |
| related | file:explicit:1bd8d133f72d4743a06a28c0 | attached via sase artifact create --bead |
| related | file:explicit:2a8b4ccda43005b5ac42e5a3 | attached via sase artifact create --bead |
| related | file:explicit:48ab8282349c800464ca383e | attached via sase artifact create --bead |
| related | file:explicit:564c89da176b9ee0c89b760b | attached via sase artifact create --bead |
| related | file:explicit:568bfb97748a4529952ee629 | attached via sase artifact create --bead |
| related | file:explicit:5c16d510615f85b8ec75fe72 | attached via sase artifact create --bead |
| related | file:explicit:8d1fcc415d3a02313416308a | attached via sase artifact create --bead |
| related | file:explicit:9307f427262857bfe7db174f | attached via sase artifact create --bead |
| related | file:explicit:abd61985c8cb0cbb748a7c26 | attached via sase artifact create --bead |
| related | file:explicit:d350cd2049aee5ae9163a022 | attached via sase artifact create --bead |
| related | file:explicit:d54703bdfa49035878bd0bdd | attached via sase artifact create --bead |
| related | file:explicit:dc86d3b302afb42ced69208b | attached via sase artifact create --bead |
| related | file:explicit:e3017580488af7834dafefb4 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

gc-measure: have the user restart their TUIs onto the instrumented code, capture busy-hour and 4-hour windows on both Python versions, attribute garbage and survivors by type and producer, correlate long pauses with swap, and report against sase-1f3's targets.

## Notes

[2026-10-20T19:30:51Z · sase-1nf.13] gc-measure partial progress 2026-10-20: verified gc-instrument at HEAD aae7eae667 (source_revision reader, census flag SASE_TUI_GC_CENSUS, freeze_report --acceptance all present and working). Pre-restart baseline: athena (py3.14.7) all retained instances FAIL sase-1f3 (idle p95 1.4-3.2s vs 500ms, GC 6-15% vs <3%, hitches 2-6.3% vs <0.5%, RSS +1.6-3.9GiB, swap up to 329MiB); apollo (py3.12.3) also multi-second idle collections (e.g. p95 0.874s, GC 2.38-4.23%). Zero tui_gc_census rows on either host. BLOCKED on: (1) installed code predates instrumentation -- primary checkout /home/bryan/projects/github/sase-org/sase is at 682e52fc71 with 0 source_revision refs, and both TUIs run old code (0 startup rows carry source_revision; athena TUI pid 2720414 since Oct17; apollo pid 554302 old). Landing/host update must deliver aae7eae667 to the installed TUI first. (2) user must then restart TUI(s) with SASE_TUI_GC_CENSUS=1; confirm via startup rows carrying source_revision. (3) then wait 20+ min, capture busy-hour + 4h windows per host via monitor, attribute garbage/survivors by type+producer, correlate pauses with fault deltas/VmSwap, write report to research sidecar 202610 dir, attach via sase bead ref add, and close sase-1f3 noting the 24h soak moved to gc-fix acceptance (gc_soak=no). Bead left OPEN; nothing closed.

[2026-10-20T19:31:50Z · sase-1nf.13] gc-measure recheck 2026-10-20 (2nd pass): still blocked, state refined. Athena primary checkout still at 682e52fc71 (0 source_revision refs) and TUI pid 2720414 (since Oct17) predates instrumentation; needs installed-code update past aae7eae667 THEN restart with SASE_TUI_GC_CENSUS=1. Apollo differs: its checkout IS at aae7eae667 (source_revision reader present) but its TUI has not restarted onto it (0 startup rows carry source_revision); apollo needs restart-with-flag only. Census rows still 0 on both hosts; SASE_TUI_GC_CENSUS unset on athena. Pre-restart acceptance baselines stand (see prior note). Next runner after user acts: confirm startup rows carry source_revision, wait 20+ min, capture busy-hour + 4h windows per host via monitor, attribute, report to research sidecar 202610 dir, ref-add, close sase-1f3 noting soak moved to gc-fix (gc_soak=no). Bead left OPEN; nothing closed.

[2026-10-20T19:35:47Z · sase-1nf.13] gc-measure recheck 2026-10-20 (3rd pass): still BLOCKED — Q1 "Both restarted" does not match observed state. Athena: primary checkout 682e52fc71, installed 682e52fc7, TUI pid 2720414 (since Oct17); 0 source_revision rows in tui_startup.jsonl, 0 tui_gc_census rows, no SASE_TUI_GC_CENSUS in TUI environ — needs installed-code update past aae7eae667 THEN restart with SASE_TUI_GC_CENSUS=1. Apollo: checkout+installed at aae7eae667, but TUI pid 554302 (since Oct15) never restarted; only latest startup row f92735c0 (19:33Z) carries source_revision, 0 census rows, no census flag in environ — needs restart-with-flag only. Pre-restart acceptance baselines stand (tools/tui_freeze_report --acceptance on athena still overall FAIL: idle p95 1.4-3.2s, GC 9-13%, hitches 3.6-6.3%, RSS +1.5-1.8GiB, swap up to 329MiB). Next runner after user acts: confirm startup rows carry source_revision on both hosts, wait 20+ min, capture busy-hour + 4h windows per host, attribute, report to research sidecar 202610 dir, ref-add, close sase-1f3 noting soak moved to gc-fix (gc_soak=no). Bead left OPEN; nothing closed.

[2026-10-23T13:23:24Z · sase-1nf.13] PROPOSED FOLLOW-UP: Correct unsorted idle p95 in tools/tui_freeze_report — summarize_instance passes chronological idle_pauses directly to _percentile while pause_stats_by_trigger sorts them. On retained 2026-10-21 16:30–20:35Z windows, athena 6135f61c prints acceptance idle p95 1.187s but sorted idle p95 is 1.823s; apollo f268269c prints 0.562s versus 0.687s. This is present at base 92d271364cb5 and can misclassify the 500ms target. Use sorted samples and a deliberately non-monotonic regression fixture; this operational phase uses the sorted by-trigger statistic in its evidence.

[2026-10-23T13:28:26Z · sase-1nf.13] PROPOSED FOLLOW-UP: Make freeze-report acceptance distinguish incomplete coverage and late-hitch violations — evaluate_acceptance at base 92d271364cb5 can print overall PASS with j/k n/a and a window shorter than 4h; it has no verdict for late hitches outside idle collection. Apollo 37fe2f80 over 2026-10-23 09:40–10:40Z prints PASS despite both missing requirements. Athena 6135f61c has a 2.082s late recovery at 2026-10-21T17:55:27Z with backstop+automatic overlap, which the existing verdict ignores. Preserve unknown/insufficient coverage separately from passing the full sase-1f3 contract; do not use the overall CLI string as full acceptance evidence.

[2026-10-23T13:29:22Z · sase-1nf.13] CHECKPOINT 2026-10-23: Both hosts now have instrumented startups at 92d271364cb5, but current TUI environments omit SASE_TUI_GC_CENSUS and SASE_TUI_PERF, and retained active+rotated logs contain zero census rows on either host. Preserved raw logs as file:explicit:8d1fcc415d3a02313416308a (athena) and file:explicit:9307f427262857bfe7db174f (apollo), reproduction bundle file:explicit:d372db3f9c249bb0a0b1cf6c, and attached measurement checkpoint file:explicit:1bd8d133f72d4743a06a28c0. Read checkpoint through sase artifact read before continuing. Matching source 54779b62 windows with >4h heartbeat coverage show sorted idle p95 1.823s/0.687s (both FAIL), GC 1.31%/1.13%, RSS -0.103/+0.259GiB, swap 0. Recent Athena hour has idle p95 2.267s, GC 3.37%, hitches 0.921%, RSS +1.474GiB; Apollo workload is quieter and not comparable busy-hour proof. Long post-instrumentation pauses often have zero major faults; census/type and per-producer attribution remain unmeasured. Two report correctness issues recorded separately as PROPOSED FOLLOW-UP. No epic symbols remain. User must fully quit both TUIs and launch SASE_TUI_GC_CENSUS=1 SASE_TUI_PERF=1 sase tui from normal shells; an in-app restart cannot add flags. After response, verify actual new startup/census rows, then use sase_monitor for 20min warmup and >=4h windows; no 24h soak here (gc_soak=no). Finish ranked producer report in research/202610, attach, and close ONLY sase-1nf.13 per current user instruction. Earlier remainder is an external setup blocker, not an oversized coding phase; one analysis agent can finish once data exists. No source or memory edits; research repo opened but unchanged.

[2026-10-23T13:35:08Z · sase-1nf.13] RESTART VERIFICATION 2026-10-23 13:34 UTC (09:34 EDT): Q1 answered Both restarted with flags, but live evidence still shows Athena PID 2826528, instance 0ca536bf, startup 11:28:35Z; Apollo PID 554302, instance bf164020, startup 11:28:41Z. Both source_revision 92d271364cb5a8c20293c0a9707a31db04b6d429. Both /proc environments omit SASE_TUI_GC_CENSUS and SASE_TUI_PERF; active plus rotated stall logs contain zero tui_gc_census rows. Latest heartbeat confirms each old instance remains active. No valid census window has started. Existing checkpoint file:explicit:1bd8d133f72d4743a06a28c0 remains applicable. No source/memory changes; epic-symbols still empty. Requesting actual full quit and shell relaunch, with host/time response to avoid ambiguous confirmation. Next continuation: verify environments, new startup identities and actual census rows, then monitor >=20min warmup plus >=4h same-instance capture (allow an extra heartbeat interval for full RSS coverage), preserve logs, complete producer attribution/report, close ONLY this phase; gc_soak=no. This is still one-agent operational analysis gated on external capture prerequisites, not an oversized coding remainder.

[2026-10-23T13:48:17Z · sase-1nf.13] RESTART CHECK 2026-10-23 13:46 UTC: Both TUIs HAVE been fully relaunched since the last note: Athena PID 3306893, instance fbcc162f, startup 13:37:19Z; Apollo PID 414896, instance cf9f1297, startup 13:37:28Z. Both run instrumented source 92d271364cb5a8c20293c0a9707a31db04b6d429. However both new process environments still omit SASE_TUI_GC_CENSUS and SASE_TUI_PERF, and both active+rotated stall logs still have zero tui_gc_census rows. Both command lines are sase -p tui beneath an interactive zsh in tmux. Thus this is now missing launch flags, not failure to restart; no valid census window has begun. Use env SASE_TUI_GC_CENSUS=1 SASE_TUI_PERF=1 /home/bryan/.local/bin/sase tui in the actual pane on EACH host after quitting its TUI. This directly sets the child environment and bypasses shell aliases/functions; do not prefix an ssh/tmux attachment or use in-app restart. Current code reads census opt-in dynamically from os.environ and no evidence identifies a code-side flag loss. Prior checkpoint file:explicit:1bd8d133f72d4743a06a28c0 remains applicable. epic-symbols has no entries; no source/memory changes. Remaining work is one-agent operational attribution after user setup and monitored >=20min warmup plus >=4h same-instance data, not an oversized coding remainder. Verify real new startup IDs, both process flags, and actual census rows before starting that window; preserve logs before rotation, finish ranked producer report in research/202610, close ONLY this phase, gc_soak=no.

[2026-10-23T14:06:21Z · sase-1nf.13] CAPTURE READY 2026-10-23 14:05 UTC: Verified real census-enabled launches on BOTH hosts at 09:54 EDT. Athena PID 3821218 / instance 03f51423 / startup 13:54:05.717918Z / Python 3.14.7; Apollo PID 447205 / instance f3763ffa / startup 13:54:05.964174Z / Python 3.12.3. Both source_revision 92d271364cb5a8c20293c0a9707a31db04b6d429, both process environments have SASE_TUI_GC_CENSUS=1 and SASE_TUI_PERF=1, and each has actual tui_gc_census rows. Preserved launch proof, initial raw logs, frozen report, capture script and analysis checkpoint as file:explicit:d54703bdfa49035878bd0bdd. Capture script initial run succeeds; it samples both hosts read-only every 120s, preserves exact new JSONL lines across rotation plus wall/monotonic clock pairs and

… and 16107 more characters

## References

- research:202610/tui\_gc\_measurement\_20261023.md

## Dependencies

- **Depends on:** [sase-1nf.12](sase-1nf.12.md) ✓ · ⧖ 2026-10-20
- **Blocks:** [sase-1nf.14](sase-1nf.14.md) ◐ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.13.md) | [sase-1nf.13](sase-1nf.13.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--research | [`sase--research@5ca8834`](https://github.com/sase-org/sase--research/commit/5ca8834314d253e69ad67ffea782e42fd637fcd1) | docs(research): record verified four-hour TUI GC measurements | [sase-1nf.13](sase-1nf.13.md) | 2026-10-23 22:34:58 EDT |

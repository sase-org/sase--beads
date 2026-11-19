# Bead: sase-1t3.13 — Interaction latency after the heap shrinks

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.13` · **Size:** large
**Created:** 2026-11-16 07:57:56 EST · **Closed:** 2026-11-18 19:57:57 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

interaction-pass: re-measure j/k and detail selection, then move detail-header lanes off the pump with per-agent caches and keep `,j` on the highlight path. Make clan runtime aggregation, delta-load graph copies, and bead-confirmation warmups proportional to changed or visible rows.

## Notes

[2026-11-18T20:52:35Z · sase-1t3.13.1.1] Baseline sase-1t3.13.1.1 landed on sase-1t3.13.1.1: steady-state j/k already satisfied (p95 ~10-12ms < 16ms); detail-selection, unread-jump, runtime-tick, exact-delta-copy, bead-warmup remain with measured evidence. Commands, fixture params, and JSON evidence in the phase bead note. One clean-tree PROPOSED FOLLOW-UP: clan fold bench stall-log gate trips on prompt_activity initial event.

[2026-11-18T23:23:12Z · sase-1t3.13.1.5--1] Combined integration measurements from `sase-1t3.13.1.5` (HEAD `194b1a1ef4175fe5397b8f666883ac9028cbcec3`; Python 3.14.7, Textual 8.0.1, sase 0.19.0, sase-core-rs 0.44.2; pinned/linked core `b1a0363997eb8150f8db8a425b83564faf5101f3`). Fixture and full results, exact commands, focused test list, and JSON paths are recorded on child phase `sase-1t3.13.1.5`.

Verification: combined focused suite passed 212 tests in 9.70s. Slow enrichment A/B/A kept one compute active and one latest pending request; viewport runtime patched 2 surfaced rows of 40; warmup handled at most 32 of 80 historical WAITING rows per batch and at most 4 stranded projects. Unread fast-path and graph-isolation suites passed. Keypath guard passed with provider discovery/subprocesses on worker threads only.

Already satisfied in this run: all clan-fold p95s under 16 ms; immediate detail-panel chrome p95 17.44 ms on the 2000/1000 trace fixture (under the 100 ms target); count-10 cold/warm memory and artifact resolver p50s are close to baseline. Runtime tick p95/max at 2000/1000 was 2347 ms (n=4) versus baseline 4497 ms (n=6), with p50 about 1939 versus 1960 ms. Core revision differs from baseline (`98a22b7` to `b1a0363`), host available memory was 28.9 GiB versus baseline about 39 GB, and sample counts differ, so use directional comparison.

Remaining measured misses: ordinary j/k p95 was 37.11/40.36 ms in the first run (n=19), and 20.25/17.98 ms in the isolated repeat, above the 16 ms target. Selected-tribe level-1 p95 remained 80.99/71.64 ms, and 64.58/58.49 ms on a lower-load repeat, above its 40 ms guard; higher fold levels were not reached. The clan-fold test's separate final stall-log assertion still fails on the initial `prompt_activity` record, already reproduced on the clean baseline and recorded by the baseline phase. The new selected-tribe latency miss was not clean-base compared.

The 2/8-row copy probe on 150/600-row graphs made 150/600 shallow Agent copies per delta, then retained only 2/8 new rows after share-back; deep graph copies were zero. Temporary allocation therefore still scales with roster size. Full trace contains no RSS/heap heartbeat, so this run does not establish long-session memory stability; the separate soak phase owns that evidence.

PROPOSED FOLLOW-UP: Bound temporary shallow Agent copies in exact-delta preparation to the affected relationship closure. Evidence: 2- and 8-row deltas each copied all 150/600 cached Agent rows, despite retaining only 2/8 new rows after share-back.

PROPOSED FOLLOW-UP: Investigate the combined-tree j/k p95 misses, especially selected-tribe fold navigation. Evidence: ordinary j/k remained above 16 ms on an isolated repeat; selected-tribe level 1 remained above its 40 ms guard on two runs, including a lower-load repeat. This performance miss has not been compared with clean-base code.

The full trace command exited 0 and wrote `/tmp/tui_trace_combined.json`, but logged an unhandled Textual timer `ZeroDivisionError` with zero interval. The known clan-fold false stall assertion is separately tracked by the baseline note. No source changes were made.

[2026-11-19T00:58:55Z · sase-1t3.13.1.land] PARENT PHASE CLOSEOUT — interaction-pass — 2026-11-18

Approved parent_close=close was executed; child epic sase-1t3.13.1 closed and the bead system closed this phase. Verified the phase work across .1-.5 and the landing:
- Detail-header lanes use off-pump workers with per-agent caches and stable content tokens; selection stays immediate and comma-j stays on highlight plus debounced detail.
- Runtime aggregation/patches are bounded to surfaced rows; warmup is bounded to visible and WAITING rows with lazy stranded-project sweeps and a positive follow-up timer.
- Exact-delta deep graph copies are gone. Share-back now runs on the worker, decides each identity once, and publishes a closure-consistent graph.
- At 165 rows, worker share-back was 7.33–7.40 ms; at 660 rows, 34.10–37.34 ms. Post-await scalar bookkeeping was 0.65–0.77 ms at 165 and 2.12–2.25 ms at 660; the latter measures scalar bookkeeping only, not the full apply span. The prior event-loop share-back was about 250 ms / 1,000 ms at 165 / 660 rows.

Verification: focused combined suite 254 passed in 9.51s; just fmt and just symvision passed. Required check ToolRun 5e0a93f77c4e2b8dc8d6c2d347b0980f reported 62,055 passed, 17 skipped, one unrelated axe cancellation failure and the already-recorded mypy failure in active chop-recovery epic sase-1tc.3.1 note 4. The failing test reproduced unchanged; it is corroborated on existing task sase-1tm and recorded on sase-1tc.3.1.

Remaining ordinary j/k p95 and selected-tribe fold misses were compared against 5b08952c6d and af07b78ac2, are pre-existing, and remain tracked on sase-lx. Targeted per-row transient copies remain tracked on sase-1tt. Follow-up triage from this epic remains recorded: +1 on sase-1gf/sase-lx/sase-xo, sase-1tt created, two proposals declined. The soak phase sase-1t3.14 remains responsible for the rest; no ancestor was closed.

## Dependencies

- **Depends on:** [sase-1t3.1](sase-1t3.1.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.10](sase-1t3.10.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.11](sase-1t3.11.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ✓ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.13.md) | [sase-1t3.13](sase-1t3.13.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.13.1.2][1] | Need parent epic decisions and parent phase context for the assigned child phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.13.1.2/README.md

<!-- sase:referenced-by:end -->

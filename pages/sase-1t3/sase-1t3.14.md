# Bead: sase-1t3.14 — End-to-end soak against the research baselines

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.14

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.14` · **Size:** medium
**Created:** 2026-11-16 07:57:56 EST · **Closed:** 2026-11-18 22:12:21 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

soak-verify: run a separate-instance soak with the whole epic, compare every stage's telemetry against the research baselines and targets, document the new gauge and baselines in the perf runbook, and record residual gaps.

## Notes

[2026-11-19T01:08:29Z · sase-1t3.14] SOAK STAGED: monitor z66x83 runs /tmp/sase-1t3.14-soak.sh (150m timeout): best-effort just install-venv (pin b1a0363997e matches linked core), then separate-instance ~65min soak of installed build 0.19.0+185.g194b1a1ef (contains all phase commits; workspace HEAD is 3 test/refactor splits ahead) with all telemetry redirected to ~/.sase/perf/sase-1t3.14-soak-<ts>/, periodic j/k, 2 py-spy dumps, freeze-report collection. Smoke-tested launch+quit path clean (startup row tier1/index 36 rows, live TUI untouched). Follow-up analyzes, updates perf-runbook, records follow-ups, verifies, and closes.

[2026-11-19T01:15:45Z · sase-1t3.14] SOAK NOT YET RUNNING: follow-up turn found monitor z66x83 still staged/pending ~10min after staging (no soak dir, no script/tmux/install processes); monitor --next remains armed (Ready to continue). No analysis possible yet; no files changed. The armed --next follow-up will do the stage table, epic-bead note, perf-runbook update, follow-up notes, check, epic-symbols, and close when the soak completes.

[2026-11-19T01:17:57Z · sase-1t3.14] Soak monitor z66x83 still staged/queued at 20:17 EST (~10min after staging); runner is alive (other monitors progressing) so this looks like queueing, not a dead handoff. Script intact, bead still in_progress, --next remains armed. No files changed.

[2026-11-19T01:21:26Z · sase-1t3.14] Adoption still pending ~17min: stop refused (already staged, nothing to do), so no cancel/re-stage path exists and a duplicate start is barred while it is active. Verified staged_monitor_launch.json is complete, claim reconciled, --next armed, script intact. Execution is host-supervisor-side; ending turn to leave it to adopt. No files changed.

[2026-11-19T02:49:09Z · sase-1t3.14--1] PROPOSED FOLLOW-UP: construction still 12.3s vs ~1s target — soak startup row app_construct_seconds 12.300929 (instance 7eb96199, build 0.19.0+185.g194b1a1ef, host load 11-20); trust memoization did not recover the 0.7-1s baseline on this loaded host

[2026-11-19T02:49:14Z · sase-1t3.14--1] PROPOSED FOLLOW-UP: cold provider substage 134.7s vs <1s target — startup load disk 367.6s with provider 134.71s + decode 208.44s (812 agents, artifact_index); warm provider stays 47-63s auto_refresh / 127-147s tier1 revalidate

[2026-11-19T02:49:20Z · sase-1t3.14--1] PROPOSED FOLLOW-UP: warm full loads 101-412s and agents_ready 554.8s vs ~1s / 5-6s targets — auto_refresh disk 101-169s, tier1 revalidate disk 281-412s, visible_ready 495.6s; host load 11-20, needs quiet-host re-measure to separate contention from loader cost

[2026-11-19T02:49:25Z · sase-1t3.14--1] PROPOSED FOLLOW-UP: startup mount 59.2s vs <3s target — process_start_to_on_mount 59.19s, on_mount_to_first_paint 14.11s, fallback release 69.19s (36 tier1 rows, 591 index rows); loaded host, separate-instance soak

[2026-11-19T02:49:34Z · sase-1t3.14--1] PROPOSED FOLLOW-UP: heap misses all four gates — RSS 7.29G at 30min vs <2G, gen-2 p95 8.57s (n=9) vs <=1s, blocks 35.6M vs <8M, hitch share 95.8% vs <0.5%, swap 41MB vs zero; tracemalloc current 1.15G/peak 1.35G while RSS 6.8-9.8G

[2026-11-19T02:49:39Z · sase-1t3.14--1] PROPOSED FOLLOW-UP: soak j/k paint p95 91.3s (n=23, all hitch-inflated, no busy window so gate INCOMPLETE) vs 16ms — model p50 3.1ms p95 33.7ms is healthy; bench supplement sase-1t3.13 isolated ordinary j/k p95 20.25/17.98ms still above 16ms, clan-fold 10-12ms PASS, detail chrome 17.44ms PASS

[2026-11-19T02:49:45Z · sase-1t3.14--1] PROPOSED FOLLOW-UP: overall usable list 495.6s vs 6-7s target — visible_ready 495.57s and agents_ready 554.76s on loaded host (load 11-20, second pytest suite running); storm thread/saturation fix held (0 hijack threads, saturated=false 16/16) so remaining wall is loader/GC/contention, not the storm

[2026-11-19T03:12:12Z · sase-1t3.14--2] PROPOSED FOLLOW-UP: sase tool run check red only on KNOWN mypy arg-type in src/sase/axe/_chop_batch_recovery_observations.py:85 (Mapping vs set, witness 03877e5f68acf5cd3ed2ff1147d15343, run 3607024893347565468309c379f69dc9) from axe commits d3fcb19562/df7a1a3a95, untouched by this docs-only phase (diff is only docs/contribute/perf-runbook.md)

[2026-11-19T03:12:21Z · sase-1t3.14--2] Soak-verify done: separate-instance soak graded (storm PASS, 7 stages FAIL with follow-ups), stage table noted on epic sase-1t3, perf-runbook sase-1t3 soak-verify section landed with baselines and executor-saturation gauges (tui_perf.md untouched), 8 PROPOSED FOLLOW-UP notes recorded (7 stage misses + 1 unrelated KNOWN mypy check failure), docs-only diff (only perf-runbook.md), check red solely on untouched axe file, epic-symbols empty

## Dependencies

- **Depends on:** [sase-1t3.1](sase-1t3.1.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.10](sase-1t3.10.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.11](sase-1t3.11.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.12](sase-1t3.12.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.13](sase-1t3.13.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.2](sase-1t3.2.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.3](sase-1t3.3.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.4](sase-1t3.4.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.5](sase-1t3.5.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.6](sase-1t3.6.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.7](sase-1t3.7.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.8](sase-1t3.8.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.9](sase-1t3.9.md) ✓ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.14](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.14.md) | [sase-1t3.14](sase-1t3.14.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c971a66`](https://github.com/sase-org/sase/commit/c971a665af152430100d76fee852d401f8af0c51) | docs(perf): record sase-1t3 soak-verify baselines and executor gauges | [sase-1t3.14](sase-1t3.14.md) | 2026-11-18 22:14:34 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.14--2][1] | Need bead state before closing soak-verify after check triage | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.14.md

<!-- sase:referenced-by:end -->

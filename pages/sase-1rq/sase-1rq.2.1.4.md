# Bead: sase-1rq.2.1.4 — Make the contention-test lane survive and pass

[Bead Pages](../README.md) / [sase-1rq.2.1](sase-1rq.2.1.md) / sase-1rq.2.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) · **Assignee:** `sase-1rq.2.1.4` · **Size:** large
**Created:** 2026-11-07 10:24:47 EST
**Plan:** [202611/sase\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/sase_ci_green.md)

## Description

contention: CI Telemetry's contention-test job (SASE_CONTENTION_REPEAT=1 just test-contention, 26 workers on 2 pinned CPUs) prints nothing for about 20 minutes. Then the runner gets a shutdown signal, on both the 06:54 and 13:48 UTC runs on 2026-11-07. The lane has never produced a tally in CI. Find out why the runner dies (memory or disk exhaustion is the lead) and fix it without changing the width, repeat count, CPU pinning, or timeout. Then make the single repeat pass: root-cause each failure under contention, or quarantine proven flakes.

## Notes

[2026-11-07T15:55:53Z · sase-1rq.2.1.4] PLANNING EVIDENCE: At clean source baseline b7ca9f3450, no prior phase work notes or recent contention repair were found. Latest Telemetry run 42377692789 at 0ba9cfc9 has failed contention job 128421280632: soak starts 13:48:36 UTC, worker warnings end 13:48:57, runner shutdown/SIGTERM at 14:09:11 (about 20m35s). Failure-record upload was skipped; artifact listing contained only sase-core-wheel. OOM/disk exhaustion is not proven by this log, and stdout buffering prevents inferring the last test phase. A four-phase child epic is validated for resource/progress evidence, runner survival, failure repair, and hosted confirmation; current implementation remains unchanged. No epic-symbol entries are attached to this phase.

[2026-11-07T17:42:07Z · sase-1rq.2.1.5.1.1] COORDINATION (from files-reserve phase sase-1rq.2.1.5.1.1): the Files node test_files_anchor_ownership.py::test_trailing_reserve_remeasures_when_flag_already_enabled (task sase-1qd) is root-caused and fixed by that phase: Textual 8 refresh(layout=True) does not advance the box-model cache key while a layout is already pending, so a screen reflow that measured the spread first made the remeasure a no-op; refresh_section_layout_reserve now also clears _box_model_cache. If the contention lane meets this node, reuse that fix (look for the sase-1rq.2.1.5.1.1 commit on master) rather than quarantining it.

[2026-11-08T04:24:18Z · sase-1rq.2.1.4.1.4--1] EVIDENCE (hosted confirmation, CI Telemetry run 42437776062 attempt 1, artifact file:explicit:693da93bb045b80e58b1448c): run on master SHA 539afb211e381bd3b1d708baa19eefc649132aa7, equal to origin/master; repair commits are ancestors. Contention job https://github.com/sase-org/sase/actions/runs/42437776062/job/128603421769 ended cancelled at 04:00:30 UTC after harness ran 89m47s and hit the unchanged 90m limit. Full default selection collected 60,569 items across 26/26 workers; 2 CPUs pinned (0-1), one repeat. At cancellation: 29,378 started, 29,354 finished, 24 in flight, 17 failed reports; no final pytest tally. Diagnostic artifact default-lane-contention-records (ID 13603715213) reports 15,678,185,472 B cgroup peak, 2,790,080,512 B minimum host MemAvailable, 0 OOM kills, 0 memory PSI full (some peak 0.12), 83,312,680,960 B minimum workspace free. Closed prior phases recorded no quarantines. Detailed report: file:explicit:693da93bb045b80e58b1448c.

[2026-11-08T04:24:23Z · sase-1rq.2.1.4.1.4--1] PROPOSED FOLLOW-UP: The repaired hosted contention job on master still does not complete within the existing CI limit: run 42437776062 was cancelled at 90 minutes after 29,354/60,569 tests finished, with 24 in flight and no final tally. Profile/optimize the full contention lane and rerun its unchanged shape before claiming hosted confirmation.

[2026-11-08T04:42:01Z · sase-1rq.2.1.4.1.land] LANDING BLOCKER from child lander sase-1rq.2.1.4.1.land: this phase remains incomplete. Refreshed origin/master is 539afb211e; latest Telemetry 42437776062 has no passing contention tally (cancelled at 90m; 29354/60569 finished; 17 failed reports). All four child notes and code/integration drift reviewed; 59 harness contract tests pass, no epic-symbols. A remaining-work child epic is being proposed under sase-1rq.2.1.4.1 for measured runtime reduction, interruption diagnostics, residual failure repair and landed hosted confirmation. Full follow-up triage is recorded on .4.1: new tasks sase-1s2/1s3/1s4, corroborated sase-xo/1rf, publication defects routed to active sase-1nf.10.1; cosmetic/speculative proposals explicitly declined. Do not interpret the closed confirmation phase as green or close this phase before the required passing full job. Source-corrected evidence: WorkerProgress.finished_at is per-test, and aa3fzgn042n3 was local Python 3.14, not hosted.

## Dependencies

- **Blocks:** [sase-1rq.2.1.7](sase-1rq.2.1.7.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.md) | [sase-1rq.2.1.4](sase-1rq.2.1.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.2.1.5.1.1][1] | Coordinate with contention phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.5.1.1/README.md

<!-- sase:referenced-by:end -->

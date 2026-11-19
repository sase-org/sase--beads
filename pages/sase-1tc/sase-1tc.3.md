# Bead: sase-1tc.3 — A scheduler stop never silently drops a chop's launch batch (sase-1c2)

[Bead Pages](../README.md) / [sase-1tc](README.md) / sase-1tc.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1dg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dg.md) · **Assignee:** `sase-1tc.3` · **Size:** large
**Created:** 2026-11-17 11:19:26 EST · **Closed:** 2026-11-19 05:22:57 EST
**Plan:** [202611/backlog\_epic\_cmdsub\_retries\_launches.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_cmdsub_retries_launches.md)

## Description

chop_launch: journal in-flight chop launch batches and resume them idempotently after a scheduler or service-host stop, with visible notices.

## Notes

[2026-11-18T00:13:46Z · sase-1tc.3] Planning evidence: inspected sase 07aedfc8ca and linked sase-core c5e60d78; phase had no prior work notes and no epic-symbol entries. Existing ordinary clan launch records batch results only after the multi-prompt call returns. Side-effect-free injected SystemExit(143) after 2/4 simulated spawns yielded zero batch progress callbacks; no real agents or runtime state were changed. Typed admission already has durable unit journals but needs original-bundle linkage and startup recovery. Authored and twice validated a five-phase sequential child epic (journal, ordinary_launch, typed_launch, recovery, acceptance), parent_bead=sase-1tc.3, including explicit clan-generation cancellation and a disposable subprocess stop/resume demonstration. Submitting through sase plan propose; implementation and closure remain for approved child work and its land agent.

[2026-11-18T11:55:58Z · sase-1tc.3.1.5] TASK RESOLVED: sase-1c2 — Added isolated subprocess coverage for ordinary and typed chop batch restart recovery, kill boundaries, SIGTERM pause, cancellation, notices, and idempotent restart; fixed recovery ownership and clan cancellation races. Focused regressions: 89 passed. Manual demo: spawn-before-ack SIGKILL recovered the remaining 3 of 4 exactly once, then a second restart launched 0; cancellation demo retained cancelled state and removed the launch receipt. Full sase tool run check ba8ef87f6437b5613155426b30e3979a passed.

[2026-11-18T12:17:24Z · sase-1tc.3.1.land] NOTE FROM sase-1tc.3.1.land: the TASK RESOLVED: sase-1c2 evidence in note #2 came from a harness that faked chop-agent records as cl_name=<agent name>. Production records use the project name or VCS ref, and the recovery code matches on that field, so spawn-before-ack reconciliation does not work in production. Child-epic remaining work under sase-1tc.3.1 fixes this and will record superseding TASK RESOLVED evidence here. Do not treat sase-1c2 as resolved until then.

[2026-11-18T20:24:50Z · sase-1tc.3.1.6.4] TASK RESOLVED: sase-1c2 — production-shaped chop batch recovery re-proved end to end. This supersedes note #2 here, which rested on fakes with an impossible cl_name evidence shape. Harness now uses real chop-agent linkage records written from launch env (cl_name=sase project name), the real name registry, explicit pipe/file handshakes, an isolated SASE state root, a disposable job and harmless short-lived processes. 17 subprocess scenarios green on ordinary AND typed paths: k-of-n k=0/2/4; SIGKILL after spawn-before-ack (dismissed agent) and after reservation-before-spawn; SIGTERM finishing the current launch; second restart launches zero everywhere; routine/manual race (loser blocked live-owner, no duplicate, exactly one interrupted+resumed); clan kill while paused, while recovery-active (crossing member settles, rest never start), and typed equivalents; multi-clan batch (unrelated clan and stale generation leave it alone; either clan cancels); two interruption episodes (exactly 2 interrupted + 2 resumed, 2 delivered episodes in the archived outbox, including a resume prepared by a killed recovery). Asserted per scenario: n distinct original identities, exactly n spawns, resumed linkage points at the original run+proposal index, original run history lists all n launches once, original clan/run identity, termination mode, notices+log lines. Acceptance fixes landed in this phase: (1) run history now merges pre-interruption launches backfilled from durable linkage (ordinary) plus resumed+reconstructed rows (typed), so history lists every member exactly once; (2) typed resume replays lost spawn acknowledgements for linkage-proven dispatching units instead of skipping them; (3) finish notices emit before executor release+retire, so a racing recovery cannot duplicate an episode notice or orphan the outbox. Typed first runs finalize their launched rows; typed proposals carry clan identity; fake spawns the planner-namespaced member identity. No Rust/binding changes, sase-core pin untouched. Verification: 17/17 acceptance green; focused suites green (batch recovery/replay/store 57, clan-launch/lifecycle/once-per/typed-admission/runner/inflight/tick 59+48+6); sase tool run check run a070819049c2e7ea8a5669652cb2ff29 STATE succeeded EXIT 0 (all lint incl. mypy+symvision, scoped lane 135 files). Disposable demo repeated via python -m tests.axe.chop_batch_process_harness demo: stop/resume 1 spawned then 3 remaining then 0, interrupted+resumed notices with 1-launched-3-remaining / 4-launched-0-remaining log lines; clan kill retained cancelled with cancelled notice.

[2026-11-18T22:10:41Z · sase-1tc.3.1.6.land] Closeout blocker (from sase-1tc.3.1.6 tale closeout): child epic sase-1tc.3.1.6 closed; parent epic sase-1tc.3.1 left open pending epic-symbol direct-import refactor (15 entries) + full check green. Phase sase-1tc.3 stays open until sase-1tc.3.1 closes. Outer epic sase-1tc left to its waiting land agent.

[2026-11-19T11:30:46Z · 1ea--code] Follow-up commit from this turn retires the Python clan-generation veto: the cancellation gate now trusts sase-core chop_batch_generation_matches at pin 6f8f016e, with no Python fallback. Serial focused regressions passed: 64 passed across the chop batch recovery/cancel, store, replay, process-recovery, and ACE kill suites, including test_clan_cancellation_during_launch_settles_current_and_stops_next, test_cancellation_priority_and_reconcile_selection, and test_older_generation_does_not_cancel_a_batch_without_recorded_generation. sase tool run check 2886ed157e17a3680cd65cc611971cf6 succeeded (exit 0). The host finalizer will commit this follow-up.

## Dependencies

- **Depends on:** [sase-1tc.2](sase-1tc.2.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1tc.4](sase-1tc.4.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.md) | [sase-1tc.3](sase-1tc.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1ea--code][1] | Record closeout evidence for the approved generation mirror retirement | 1 |
| read-by | [agent:sase-1tc.3.1.5][2] | Need parent phase context before recording the required TASK RESOLVED acceptance evidence | 1 |
| read-by | [agent:sase-1tc.3.1.6.2][3] | Review the prior TASK RESOLVED evidence before adding the superseding production-shaped evidence | 1 |
| read-by | [agent:sase-1tc.3.1.6.4][4] | Need parent phase acceptance and TASK RESOLVED evidence location | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ea.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.5/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.2/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.4/README.md

<!-- sase:referenced-by:end -->

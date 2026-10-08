# Bead: sase-1hf.5 — Give wait\_checks and sidecar\_auto\_sync their own routines

[Bead Pages](../README.md) / [sase-1hf](README.md) / sase-1hf.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y0.md) · **Assignee:** `sase-1hf.5` · **Size:** small
**Created:** 2026-10-07 14:45:47 EDT · **Closed:** 2026-10-07 19:37:54 EDT
**Plan:** [202610/wait\_lane\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_lane_repair.md)

## Description

lane-split: new agent_waits (2 s) and sidecar_sync (30 s) routines, post-sync beads pulse, 0.5 s ready.json poll in the runner, test and docs updates, and the consolidated PROPOSED FOLLOW-UP list.

## Notes

[2026-10-07T23:36:53Z · sase-1hf.5--1] PROPOSED FOLLOW-UP: lane-split consolidated list — (1) lengthen _WAIT_DEPENDENCY_FALLBACK_INTERVAL 60s to 180-300s once telemetry shows >=90% non-fallback releases; (2) sase-core full-history query_agent_artifact_index ~11-12s for 15.7k rows and scan_agent_artifacts ~12s, likely explains bead_claim_checks ~33s runs; (3) ~2.1k leaked ..gate-shell-*/..monitor-start-*/..gate-turn-* lock files in ace-run/; (4) archive waiting.json for long-dead runners after deciding TUI/retention/lifecycle effects; (5) if release latency misses p50<=5s/p95<=15s, scoped/incremental wait resolution then report Phase 2 event-wake; (6) admission-latency parallel track (~11s capacity-only slot scan under host-wide lock) quantified by new admission_latency_s/runner_slot_wait_s keys.

[2026-10-07T23:37:17Z · sase-1hf.5--1] PROPOSED FOLLOW-UP: 5 check failures reproduce identically on clean base tree (verified via git stash 2026-10-07): test_land_failure_entry_clears_when_waiter_releases (ready.json exact-payload assert misses released_by/dependencies_satisfied_at keys from release-telemetry phase), test_muse_usage_probe_missed_mint_is_a_timeout_not_absence, test_no_system_clock_display_sites, test_fast_path_guards_mutations_but_not_reads, test_fast_path_refuses_mutation_from_plain_checkout_sidecar_record. None touched by lane-split diff.

[2026-10-07T23:37:54Z · sase-1hf.5--1] lane-split done and verified: agent_waits (wait_checks @2s) and sidecar_sync (sidecar_auto_sync @30s, no run_every) routines in default_config.yml; post-sync beads pulse in sidecar_auto_sync; runner ready.json poll 2s->0.5s with fallback cadence unchanged at 60s; fixed 8 stale 2s-poll assertions in wait/outage tests plus new lane-split contract, idle-tick, post-sync-pulse, and poll-constant tests (all pass: 53+29+50 in targeted files); docs/axe.md (nine routines) and docs/configuration.md illustration updated; ruff check+format clean; full check 14 NEW triaged — 9 fixed by this phase, 5 remaining reproduce identically on clean base tree and recorded as PROPOSED FOLLOW-UP; no epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1hf.2](sase-1hf.2.md) ✓ · ⧖ 2026-10-07
- **Depends on:** [sase-1hf.4](sase-1hf.4.md) ✓ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1hf.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1hf.5.md) | [sase-1hf.5](sase-1hf.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3a4178b`](https://github.com/sase-org/sase/commit/3a4178b15ae6af2511631c8c74852c0b868156cf) | feat(axe): split wait\_checks and sidecar auto-sync into dedicated routines | [sase-1hf.5](sase-1hf.5.md) | 2026-10-07 19:41:12 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1hf.5--1][1] | check existing notes and lane-split progress | 2 |
| read-by | [agent:sase-1hf.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1hf.5.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1hf.land/README.md

<!-- sase:referenced-by:end -->

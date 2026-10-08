# Bead: sase-1hf.4 — Resolve only live waiters from a filesystem view

[Bead Pages](../README.md) / [sase-1hf](README.md) / sase-1hf.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y0.md) · **Assignee:** `sase-1hf.4` · **Size:** medium
**Created:** 2026-10-07 14:45:46 EDT · **Closed:** 2026-10-07 18:11:20 EDT
**Plan:** [202610/wait\_lane\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_lane_repair.md)

## Description

live-waiters: shared waiting-marker walk plus tri-state runner liveness, skip dead waiters and the dependency-view build when no live waiter is pending, build the resolving view from filesystem rows instead of the slow index query, add backlog counters, and reuse the walk in sidecar_auto_sync.

## Notes

[2026-10-07T21:55:08Z · sase-1hf.4] live-waiters restart/revive answer: no path relaunches a runner in an existing artifact dir relying on a ready.json published while it was dead. _write_bootstrap_agent_meta reseeds pid + process_identity on every start (refreshed runs included) before write_waiting_marker, and wait_for_dependencies re-resolves via initial_dependencies_resolved before parking. A refreshed runner therefore reclassifies live and a stale ready.json can only pre-exist from its own earlier release. Dead waiters are safe to skip.

[2026-10-07T21:55:24Z · sase-1hf.4] live-waiters read-only timings on athena ~/.sase/projects (37 projects, 16942 artifacts, 904 waiting markers): shared walk 0.53s, liveness classification of 812 pending 0.04s (live=17 dead=795 unknown=0), filesystem view build 3.16s + add_many 4.97s = 8.1s total. Dead-only tick now costs ~0.6s (was ~24s full run); live tick ~8.7s (was ~19s index route). No job executed against the live host.

[2026-10-07T21:55:33Z · sase-1hf.4] PROPOSED FOLLOW-UP: test_land_failure_entry_clears_when_waiter_releases expects ready.json without released_by but the release-telemetry payload always includes it; fails identically on the clean base tree (verified via stash), no task bead tracks it yet

[2026-10-07T22:11:00Z · sase-1hf.4] PROPOSED FOLLOW-UP: sase tool run check fails at lint(symvision) on stale --epic-symbol sase-1h7.8(describe_epic_follow) in the Justfile (bead sase-1h7.8 is closed); entry is on clean HEAD and owned by the sase-1h7 lane, fails identically without this phase diff. Symvision findings for this phase itself are identical to base (only the two pre-existing _runs private-import items in untouched files).

[2026-10-07T22:11:20Z · sase-1hf.4] live-waiters done and verified: new sase.axe.wait_marker_scan (shared walk + alive/dead/unknown liveness, unknown fails open); wait_checks skips dead waiters and the dependency-view build when none live (reason no_live_waiters), resolves from filesystem rows (index/full-walk route removed), and reports live_waiting/dead_waiting/unknown_liveness; sidecar_auto_sync reuses the walk with identical bead-wait semantics. Tests: 191 passed across all wait_checks/sidecar/marker suites incl. 6 new dead/pid-reuse/live-pid/no-view tests + 12 new scan/liveness unit tests; docs/axe.md and wait_checks description updated; read-only host timings walk 0.53s/classify 0.04s (17 live of 904) and view 8.1s. Two base-reproducing failures recorded as PROPOSED FOLLOW-UP (epic-follow-safety payload assertion; stale sase-1h7.8 epic-symbol in Justfile reds symvision); ruff/mypy and all other check stages pass.

## Dependencies

- **Depends on:** [sase-1hf.3](sase-1hf.3.md) ✓ · ⧖ 2026-10-07
- **Blocks:** [sase-1hf.5](sase-1hf.5.md) ✓ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1hf.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1hf.4/README.md) | [sase-1hf.4](sase-1hf.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`68a4e89`](https://github.com/sase-org/sase/commit/68a4e89ac48165b789729bb117fa7261dad678ee) | feat(wait): resolve only live waiters from a filesystem view | [sase-1hf.4](sase-1hf.4.md) | 2026-10-07 18:13:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1hf.4][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1hf.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1hf.4/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1hf.land/README.md

<!-- sase:referenced-by:end -->

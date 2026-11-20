# Bead: sase-1tz.4.1.12 — Apply the tool-run log horizon on a schedule, age-rotate tui.log, and verify digest and run pruning

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.12` · **Size:** medium
**Created:** 2026-11-20 14:00:25 EST · **Closed:** 2026-11-20 15:46:45 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

log_horizons: an hourly housekeeping chop applies the existing tool-run retention owner, not only under disk pressure, and removes emptied run dirs. tui.log rotates by age as well as size. Verify error-digest pruning and that artifact_run_prune is unblocked on both hosts.

## Notes

[2026-11-20T20:08:22Z · sase-1tz.4.1.12] Before (read-only 2026-11-20): athena ~/.sase/tools/logs 1163.47 MiB, 11427 dirs, 2312 empty (all >14d), 16131 files (12558 >14d); tui.log 1.6 MiB (0d), tui.log.1-3 ~2 MiB mtime 40.6-41.1d; 732 error digests, no retention marker, oldest 137.4d; artifact_run_prune 20261120T135622 unavailable=0 selected=0 protected=24072 status=ok; error_digest chop failing exit 1 (dedup_key requires plus_one_note). apollo tools/logs 22.82 MiB, 2147 dirs, 1456 empty (900 >14d), 550 files (179 >14d); tui.log 1.6 MiB (0.1d) no rotated segments; 444 digests, no marker, oldest 81.1d; artifact_run_prune 20261120T150047 unavailable=0 nothing_reclaimable; error_digest chop failing exit 1 same cause. Lost runs all have settled_ts (athena 48, apollo 15). After-install (human): `just install` on athena and apollo so housekeeping loads state_retention and the digest prune-first/plus_one_note fix.

[2026-11-20T20:08:49Z · sase-1tz.4.1.12] Overlap sase-zw.8: this phase schedules the existing tool_run_retention owner (same step as sase disk reap / disk_pressure) at most once per tool_runs.housekeeping_interval_seconds and rmdirs emptied ~/.sase/tools/logs run dirs; no second tool-run policy. clutter_reapers adds further classes to the same chop. ToolRun store already marks dead wrappers lost via reconcile with settled_ts, so no PROPOSED FOLLOW-UP for never-settled dirs. artifact_run_prune is unblocked on both hosts (unavailable=0). error_digest prune was not holding its 30d/keep-50 horizon because notify crashed before prune; notify now passes plus_one_note and prune runs first.

[2026-11-20T20:46:16Z · sase-1tz.4.1.12] PROPOSED FOLLOW-UP: completion snapshot drift on sase artifact link list description_digest (current 78d06bb630b5c438 vs snapshot 838688e99f9eedec) — parser_artifact_link.py is unchanged by this phase; run just sync-completion-spec on a clean tree. just check NEW tests/completion/test_snapshot.py.

[2026-11-20T20:46:45Z · sase-1tz.4.1.12] Hourly state_retention applies existing tool_run_retention without pressure (interval-gated) and rmdirs empty ~/.sase/tools/logs run dirs; tui.log rotates by 14d age and prunes numbered backups; error-digest prune now runs first and notify passes plus_one_note (was crashing, 732/444 stale digests); artifact_run_prune unavailable=0 on athena and apollo. Targeted tests passed. just check lints green; remaining completion snapshot drift on sase artifact link list is unrelated (PROPOSED FOLLOW-UP). After-install: just install on both hosts.

## Dependencies

- **Blocks:** [sase-1tz.4.1.13](sase-1tz.4.1.13.md) ◐ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.12/README.md) | [sase-1tz.4.1.12](sase-1tz.4.1.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`18e4f35`](https://github.com/sase-org/sase/commit/18e4f35a54d84c71e79d41d2bd74cabc8771429c) | feat(retention): schedule tool-run log horizon and age-rotate tui.log | [sase-1tz.4.1.12](sase-1tz.4.1.12.md) | 2026-11-20 15:50:07 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.12][1] | Need current notes, parent IDs, and phase close requirements before host measurements and close | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.12/README.md

<!-- sase:referenced-by:end -->

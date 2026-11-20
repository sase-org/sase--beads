# Bead: sase-1tz.4.1.13 — Fix the proc log-lock and registry temp-file leaks and reap their backlog

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.13` · **Size:** medium
**Created:** 2026-11-20 14:00:25 EST · **Closed:** 2026-11-20 16:56:14 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

clutter_reapers: deleting proc logs also removes their lock files. The name-registry writer sweeps its own stale temp files under its lock. Owner steps reap both backlogs from the log_horizons chop. Index backups follow the index_backups decision.

## Notes

[2026-11-20T21:49:02Z · sase-1tz.4.1.13] Before (read-only 2026-11-20): athena ~/.sase/procs/logs 599 entries (596 .log, 3 .log.1) + 13713 .log.lock files, dir 19 MiB; 596 locks have a live .log sibling, oldest lock 2026-08-13; registry tmps 9 files 82 MiB (oldest Jul 24); index backups: 222261248 B .bak (Sep 26) + 32768 B -shm + 0 B -wal = 212 MiB total. apollo procs/logs 55 .log + 0 .log.1 + 6757 locks, dir 568 KiB; 55 locks have a live .log sibling; registry tmps 3 files 22 MiB; no index backups; live index 121876480 B. After-install (human): `just install` on athena and apollo so housekeeping loads the proc_log_lock_sweep/registry_tmp_sweep owners and the report-only backup row.

[2026-11-20T21:49:28Z · sase-1tz.4.1.13] Overlap sase-zw.8: clutter_reapers adds proc_log_lock_sweep + registry_tmp_sweep owners to the same state_retention chop that log_horizons created, plus a procs/logs inventory row and a report-only agent_index_backups row (never auto-deleted per index_backups=report). No second tool-run policy; managed-temp safety and inventory discovery stay with sase-zw.8.7.8. Staged one-time delete gate custom-a71ace61-4f81-43f5-af89-2b0d2b74b315 for the athena Sep 26 222 MiB backup.

[2026-11-20T21:49:35Z · sase-1tz.4.1.13] PROPOSED FOLLOW-UP: 9 tests in tests/core/test_disk_footprint_inventory.py fail with sase_core_rs disk-inventory wire stale (expected 2, installed wheel provides 1); reproduces identically on the clean base tree via plain uv run pytest (check setup rebuilds core from the linked checkout, so sase tool run check is unaffected). Needs a sase-core pin bump past the wire-2 commit, owned by whichever phase moves sase-core-revision.txt.

[2026-11-20T21:56:14Z · sase-1tz.4.1.13] Done and verified: delete_proc_logs removes the proc lock file under its flock (missing lock stays quiet); write_registry sweeps stale .agent_name_registry.json.*.tmp siblings under the mutation lock (all write paths confirmed locked); state_retention runs new proc_log_lock_sweep + registry_tmp_sweep owners every pass and both join run_disk_reap (visible in sase disk list/reap, pressure recovery, hourly chop); index_backups=report implemented as a report-only inventory row naming the owner in pressure notices, nothing auto-deleted, one-time athena 222 MiB backup delete proposed via staged gate custom-a71ace61. Focused suites pass (proc logs, lock sweep, tmp sweep, clutter rows, config, state retention); sase tool run check lints green (incl. symvision/mypy) and scoped lane 62576 passed with only pre-existing/flake failures (snapshot drift + hijack canary KNOWN, gate-capacity FLAKY, bare-git/monitor flakes pass on re-run, snapshot structural drift reproduces on clean base).

[2026-11-20T22:06:43Z · sase-1tz.4.1.13--1] Gate custom-a71ace61 verified: athena agent-index backup files deleted (.bak 222261248 B + .bak-shm 32768 B + .bak-wal 0 B = 222294016 B / 212.0 MiB reclaimed); no .bak* files remain, live index agent_artifact_index.sqlite (375300096 B) untouched.

## Dependencies

- **Depends on:** [sase-1tz.4.1.12](sase-1tz.4.1.12.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.1.13.md) | [sase-1tz.4.1.13](sase-1tz.4.1.13.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.13--1][1] | verify gate follow-up: check backup deletion | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.1.13.md

<!-- sase:referenced-by:end -->

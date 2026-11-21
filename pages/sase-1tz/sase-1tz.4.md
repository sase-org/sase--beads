# Bead: sase-1tz.4 — Gateway checkpoint fix, notification hygiene, and retention sweep (items 11-13)

[Bead Pages](../README.md) / [sase-1tz](README.md) / sase-1tz.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1eb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1eb.md) · **Assignee:** `sase-1tz.4` · **Size:** xlarge
**Created:** 2026-11-19 07:09:39 EST
**Plan:** [202611/notification\_log\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/notification_log_audit_fixes.md)

## Description

hygiene: handle SQLite's busy -1 checkpoint result and serve snapshots stale-while-revalidate. Fix the remaining notification dedup, amplification, orphan, blob-size, and no-op-write issues. Add age-based reapers that apply the stated log and state retention horizons.

## Notes

[2026-11-20T20:08:56Z · sase-1tz.4.1.12] log_horizons: hourly state_retention applies tool_run_retention without pressure; tui.log ages at 14d; digest prune unblocked; artifact_run_prune unavailable=0 on both hosts.

[2026-11-20T20:22:57Z · sase-1tz.4.1.8] triage_volume (sase-1tz.4.1.8): measured before — athena 36.1 triage rows/day, 2.35 rows per bead-kind (max 27); apollo 31.5/day, 2.42 (max 27); +1 evidence drives 72% of 2142 gate recreations. Re-presentations now refresh one adopted row in place; quiet-task-beads removed from chezmoi source (takes effect on chezmoi apply). After-install command is on sase-1tz.4.1.8.

[2026-11-20T20:23:40Z · sase-1tz.4.1.11] state_refresh_memo BEFORE (2026-11-20): retained check logs showed Apollo 530 warning diagnostics/day and max 232 repeats/run over 7 days; Athena 488/day and max 126 repeats/run over 6 retained days. Full daily counts and the repeatable after-install scan command are on sase-1tz.4.1.11.

[2026-11-20T20:25:56Z · sase-1tz.4.1.3] attention_key (sase-1tz.4.1.3) before: athena 1,649 remote-attention rows all-time (96 live, 21 undismissed), 66 requests with 2-3 per-revision rows; apollo 0. After-install jq command recorded on sase-1tz.4.1.3.

[2026-11-20T20:37:41Z · sase-1tz.4.1.6] wait_blocker (sase-1tz.4.1.6): wait_checks now raises one frozen notice per failed root blocker (direct + transitive waiters, no +1 on unchanged passes); before: athena 409 undismissed per-waiter rows / 115,862 +1s, apollo 59 / 8,906 — repeat command on sase-1tz.4.1.6.

[2026-11-20T21:29:08Z · sase-1tz.4.1.10] notify_quieting (sase-1tz.4.1.10): file-hooks successes -> 1 silent row/hook (athena 160 ok rows, apollo 208 before); workspace-rescue keyed per workspace+cause (athena 197 rows -> 75 keys); prune nudge floor 1 GiB or disk pressure; no-op hold ledger rows removed (athena 481 on 11-19). Before-numbers and after-install command are on sase-1tz.4.1.10.

[2026-11-20T21:55:56Z · sase-1tz.4.1.13] sase-1tz.4.1.13 clutter_reapers done: proc log deletes now remove lock files; registry writer sweeps stale tmps under lock; hourly state_retention reaps both backlogs; index backups are report-only with a staged one-time delete gate for the athena 222 MiB backup.

[2026-11-20T23:53:10Z · sase-1tz.4.1.5] blob_adopt baseline (sase-1tz.4.1.5): before wrapper install, athena 5,123,812 live bytes / 2,252 rows / 3,358,579 payload bytes / 76 rows over 8 KiB / 452 broken files; apollo 4,187,514 / 1,709 / 3,216,430 / 69 / 352. Repeatable after-install command is recorded on sase-1tz.4.1.5.

## Dependencies

- **Depends on:** [sase-1tz.3](sase-1tz.3.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) | [sase-1tz.4](sase-1tz.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.5][1] | Need the parent phase record for its notification size measurements | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.5/README.md

<!-- sase:referenced-by:end -->

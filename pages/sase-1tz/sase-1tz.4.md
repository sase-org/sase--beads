# Bead: sase-1tz.4 — Gateway checkpoint fix, notification hygiene, and retention sweep (items 11-13)

[Bead Pages](../README.md) / [sase-1tz](README.md) / sase-1tz.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1eb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1eb.md) · **Assignee:** `sase-1tz.4` · **Size:** xlarge
**Created:** 2026-11-19 07:09:39 EST · **Closed:** 2026-11-21 07:38:20 EST
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

[2026-11-21T12:37:36Z · sase-1tz.4.1.land] sase-1tz.4.1 land agent, filling the summaries three phases skipped. wal_busy (sase-1tz.4.1.1): busy -1 checkpoints report checkpoint_busy, and the gateway hook runs PASSIVE after waiters wake. Before (measured at landing): apollo gateway log 2026-11-14..21 had 0 'out of range integral' / 0 'checkpoint failed' lines; athena's gateway log is empty (no traffic). Command on sase-1tz.4.1.1. gateway_swr (sase-1tz.4.1.2): expired snapshots are served at once as 'revalidating' for 5 min with one background rebuild, and permit waits are bounded. Before: apollo 6,480 builds, 3 over 60 s, max 29m56s, 137 timed-out waiters, 5 HTTP 504s. Command on sase-1tz.4.1.2. gate_reconcile (sase-1tz.4.1.9): dismissed pending triage/snooze/flag gates cancel and stay suppressed, and settled bundles older than 30 d are reaped at 100 per pass. Before: athena 3,627+24 and apollo 1,128+7 settled bundles older than 30 d; 0 dismissed-pending. Command on sase-1tz.4.1.9.

[2026-11-21T12:38:39Z · sase-1tz.4.1.land] VERIFIED (sase-1tz.4.1 land agent): child epic sase-1tz.4.1 completed all of this phase's items 11-13 (F11 gateway WAL checkpoint and snapshot waits, F12 notification hygiene, F13 log and state retention). All 13 child phases landed on sase 39b594a30c. The sase-core pin 6524f378 contains every phase's core commit, and sase-telegram bffd4f6 and chezmoi 058b195b are pushed. 286 focused tests and phase .5's combined-tree check e09f2dea pass. Every measuring phase has before-numbers and an after-install command on its own bead and a summary here (wal_busy, gateway_swr, and gate_reconcile summaries added at landing). Live acceptance waits on the human's just install plus chezmoi apply on athena and apollo. Closing sase-1tz.4.1 auto-closed this phase ('delegated work landed'), and that close is correct. Parent epic sase-1tz is left to its own land agent.

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
| read-by | [agent:sase-1tz.4.1.5][1] | Verify blob_adopt measurement summary already recorded on the parent phase | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.5/README.md

<!-- sase:referenced-by:end -->

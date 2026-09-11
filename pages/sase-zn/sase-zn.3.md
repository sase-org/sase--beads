# Bead: sase-zn.3 — Stop re-parsing the whole notification store on every refresh tick

[Bead Pages](../README.md) / [sase-zn](README.md) / sase-zn.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.03` · **Assignee:** `sase-zn.3` · **Size:** medium
**Created:** 2026-09-11 12:20:21 EDT · **Closed:** 2026-09-11 17:07:31 EDT
**Plan:** [202609/ace\_typing\_lag\_athena.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_typing_lag_athena.md)

## Description

notif-snapshot: cache the parsed notification snapshot against a cheap change token and bound the active notifications.jsonl so a 13.6 MB re-parse stops running on the TUI refresh cadence.

## Notes

[2026-09-11T21:06:57Z · sase-zn.3] PROPOSED FOLLOW-UP: Live notifications.jsonl still averages ~9KB/row because action_data inlines large payloads (p50 1.6KB, p95 19KB, max 1.9MB) — reference those payloads instead of inlining so dismissed-row compaction cannot bound the store

[2026-09-11T21:07:31Z · sase-zn.3] Cached read_current_notifications_snapshot on path+include_dismissed+mtime/size/inode so an unchanged live file is not re-parsed; due next_snooze_deadline still busts the cache and expired_ids are not replayed. Added notification_store_compact housekeeping chop that archives dismissed rows past the 14-day horizon while keeping unread and actionable rows in the live file (verified 1001 old dismissed archived, unread+PlanApproval kept). Tests: unchanged store one rust read, changed store reparses, writes invalidate, chop no_op/action summaries. Live store on this host is 13.4MB/1498 rows, ~9KB avg, with action_data as the bulk (max 1.9MB) — filed as a proposed follow-up.

## Dependencies

- **Blocks:** [sase-zn.8](sase-zn.8.md) ◐ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.3/README.md) | [sase-zn.3](sase-zn.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`45a6b87`](https://github.com/sase-org/sase/commit/45a6b875a2c84c05f5ac4ce41e918622d06c886e) | perf(notifications): cache snapshot reads and compact live JSONL hourly | [sase-zn.3](sase-zn.3.md) | 2026-09-11 17:34:59 EDT |

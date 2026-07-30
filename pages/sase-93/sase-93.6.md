# Bead: sase-93.6 — Fix spurious SQLITE\_BUSY in the sase-core telemetry store

[Bead Pages](../README.md) / [sase-93](README.md) / sase-93.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-93.6` · **Size:** medium
**Created:** 2026-07-25 11:27:32 UTC
**Plan:** [202607/restore\_green\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202607/restore_green_ci.md)

## Description

'Phase: core-sqlite-busy' section: in the sase-core repo, make write transactions use BEGIN IMMEDIATE and make the WAL journal-mode pragma contention-tolerant so concurrent telemetry writers stop failing with `database is locked`.

## Notes

COMMIT: 949ec18

## Dependencies

- **Blocks:** [sase-93.7](sase-93.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-93.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-93.6/README.md) | [sase-93.6](sase-93.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@949ec18`](https://github.com/sase-org/sase-core/commit/949ec188d602cbf80117afd9a79724315e86c796) | fix(telemetry): prevent SQLite writer lock races (sase-93.6) | [sase-93.6](sase-93.6.md) | 2026-07-25 11:49:33 |

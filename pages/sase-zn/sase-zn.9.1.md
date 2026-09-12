# Bead: sase-zn.9.1 — Make cached notification snapshots safe across concurrent writers

[Bead Pages](../README.md) / [sase-zn.9](sase-zn.9.md) / sase-zn.9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zn.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zn.land.md) · **Assignee:** `sase-zn.9.1` · **Size:** medium
**Created:** 2026-09-12 17:29:02 EDT · **Closed:** 2026-09-12 18:01:47 EDT
**Plan:** [202609/finish\_ace\_typing\_lag.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_ace_typing_lag.md)

## Description

notification_consistency: fix the snapshot/token race without restoring unchanged-store parsing or replaying snooze expiration events.

## Notes

[2026-09-12T22:01:47Z · sase-zn.9.1] Implemented notification snapshot cache token revalidation, added deterministic append/replacement/interleaved-reader/local-mutation regressions, preserved unchanged repeated-read caching; verified with pytest tests/test_core_facade/test_notification_store.py -q, pytest tests/test_github_cli.py -q, just fmt, just check (full-suite escalation passed), and epic-symbols reported no entries.

## Dependencies

- **Blocks:** [sase-zn.9.3](sase-zn.9.3.md) ◐ · ⧖ 2026-09-12
- **Blocks:** [sase-zn.9.4](sase-zn.9.4.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.9.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.9.1/README.md) | [sase-zn.9.1](sase-zn.9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5554dfb`](https://github.com/sase-org/sase/commit/5554dfb0ce7d46250422eb8c1989201a8634ca5a) | fix(notifications): guard snapshot cache token publication | [sase-zn.9.1](sase-zn.9.1.md) | 2026-09-12 18:20:10 EDT |

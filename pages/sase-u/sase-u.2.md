# Bead: sase-u.2 — Phase 2 — Move all state-mutating I/O off the UI thread

[Bead Pages](../README.md) / [sase-u](README.md) / sase-u.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-u.2`
**Created:** 2026-04-26 07:23:34 UTC · **Closed:** 2026-04-26 07:55:12 UTC
**Plan:** [202604/instant\_jk\_navigation.md](https://github.com/sase-org/sase--plans/blob/main/202604/instant_jk_navigation.md)

## Description

No action handler does synchronous file I/O on the event loop. UI thread mutates only in-memory model and schedules persistence asynchronously via tui/util/io_async.py helper.

## Notes

COMMIT: 19c0a708

## Dependencies

- **Depends on:** [sase-u.1](sase-u.1.md) ✓
- **Blocks:** [sase-u.3](sase-u.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3780207`](https://github.com/sase-org/sase/commit/3780207dc8a035b3704f2996827855f00fdaa04e) | feat: move TUI auto-approve and bulk-dismiss disk I/O off the event loop (sase-u.2) | [sase-u.2](sase-u.2.md) | 2026-04-26 07:55:16 |

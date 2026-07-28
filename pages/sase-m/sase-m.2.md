# Bead: sase-m.2 — Phase 2: Remove redundant polling sleep in Textual Pilot helpers

[Bead Pages](../README.md) / [sase-m](README.md) / sase-m.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-24 14:30:54 UTC · **Closed:** 2026-04-24 14:49:14 UTC
**Plan:** [202604/speed\_up\_slow\_tests.md](https://github.com/sase-org/sase--plans/blob/main/202604/speed_up_slow_tests.md)

## Description

Drop the extra asyncio.sleep(interval) in expect_state, expect_screen_contains, expect_screen_not_contains, and wait_for in src/sase/ace/testing.py. pilot.pause() already yields a frame tick. Verify with 3x runs to catch flakiness.

## Notes

COMMIT: 3af8a17c

## Dependencies

- **Blocks:** [sase-m.3](sase-m.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3af8a17`](https://github.com/sase-org/sase/commit/3af8a17cceb3ad2d33f9240911033b4345438524) | ref: drop redundant polling sleep in Textual Pilot helpers (sase-m.2) | [sase-m.2](sase-m.2.md) | 2026-04-24 14:49:19 |

# Bead: sase-12.1 — Phase 1 — Move kill notification I/O off the immediate path

[Bead Pages](../README.md) / [sase-12](README.md) / sase-12.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-12.1`
**Created:** 2026-04-28 22:45:10 UTC · **Closed:** 2026-04-28 22:58:55 UTC
**Plan:** [202604/tui\_perf\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_v2.md)

## Description

Mirror the dismiss-path async pattern on the kill path in src/sase/ace/tui/actions/agents/_killing.py. Drop synchronous notification I/O from _do_kill_agent and _do_bulk_kill_agents; capture dismissed_snapshot at schedule time; move dismiss_notifications_for_agents and save_dismissed_agents into the persistence worker; refresh notification count async. See plans/202604/tui_perf_v2.md (Phase 1).

## Notes

COMMIT: a838117d

## Dependencies

- **Blocks:** [sase-12.2](sase-12.2.md) ✓
- **Blocks:** [sase-12.6](sase-12.6.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`4d0c252`](https://github.com/sase-org/sase/commit/4d0c252d7a6c5268476e6606b5bcb259ca63782c) | feat: move kill notification I/O off the immediate path (sase-12.1) | [sase-12.1](sase-12.1.md) | 2026-04-28 22:58:41 |

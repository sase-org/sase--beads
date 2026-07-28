# Bead: sase-3t.4 — Phase 4 - TUI Refresh Scheduling Becomes Tier 1 By Default

[Bead Pages](../README.md) / [sase-3t](README.md) / sase-3t.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-3t.4`
**Created:** 2026-05-21 13:59:59 UTC · **Closed:** 2026-05-21 15:02:13 UTC
**Plan:** [202605/agents\_tab\_full\_refresh\_elimination.md](https://github.com/sase-org/sase--plans/blob/main/202605/agents_tab_full_refresh_elimination.md)

## Notes

COMMIT: c8857dc8f

[2026-07-27T18:59:23Z · sase-a1.6] [2026-05-21T15:01:06Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Implemented Phase 4 TUI refresh scheduling: normal Agents refresh now always requests the Tier 1 visible-inbox path, history reconcile is only armed for repair/fallback states and no longer starts a startup Tier 2 timer, and an explicit Agents leader action (,y) requests full-history refresh when needed. Added scheduling/keymap/command coverage. Validation: just install; focused venv pytest for refresh/keymap/catalog tests; just check.

## Dependencies

- **Depends on:** [sase-3t.3](sase-3t.3.md) ✓
- **Blocks:** [sase-3t.5](sase-3t.5.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`b36b9b8`](https://github.com/sase-org/sase/commit/b36b9b81676e7d5f21240218b9b4e751ec8dca38) | feat: make Agents refresh Tier 1 by default (sase-3t.4) | [sase-3t.4](sase-3t.4.md) | 2026-05-21 15:02:43 |

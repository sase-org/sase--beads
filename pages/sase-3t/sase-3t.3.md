# Bead: sase-3t.3 — Phase 3 - Core Index Query Semantics For Visible Inbox

[Bead Pages](../README.md) / [sase-3t](README.md) / sase-3t.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-3t.3`
**Created:** 2026-05-21 13:59:45 UTC · **Closed:** 2026-05-21 14:52:09 UTC
**Plan:** [202605/agents\_tab\_full\_refresh\_elimination.md](https://github.com/sase-org/sase--plans/blob/main/202605/agents_tab_full_refresh_elimination.md)

## Notes

COMMIT: 66b50628d

[2026-07-27T18:59:20Z · sase-a1.6] [2026-05-21T14:50:22Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Implemented Phase 3 core visible-inbox query semantics in ../sase-core: normal index queries now use suffix-based dismissed exclusion for terminal/stale artifact rows before active/completed limits, preserve hidden-inclusive debug/full-history inspection of dismissed rows, and include terminal workflow-state rows in the recent-completed bucket. Added focused Rust coverage for stale dismissed rows not consuming active_limit and terminal failed workflows appearing in completed results. Validation: cargo test -p sase_core agent_scan::index::tests -- --nocapture; just install; just check.

## Dependencies

- **Depends on:** [sase-3t.1](sase-3t.1.md) ✓
- **Depends on:** [sase-3t.2](sase-3t.2.md) ✓
- **Blocks:** [sase-3t.4](sase-3t.4.md) ✓

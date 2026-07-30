# Bead: sase-3t.1 — Phase 1 - Visible-Inbox Contract And Wire Shape

[Bead Pages](../README.md) / [sase-3t](README.md) / sase-3t.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-3t.1`
**Created:** 2026-05-21 13:59:10 UTC · **Closed:** 2026-05-21 14:20:37 UTC
**Plan:** [202605/agents\_tab\_full\_refresh\_elimination.md](https://github.com/sase-org/sase--plans/blob/main/202605/agents_tab_full_refresh_elimination.md)

## Notes

COMMIT: e0badcfaa

[2026-07-27T18:59:13Z · sase-a1.6] [2026-05-21T14:15:39Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Implemented visible-inbox contract and wire shape. Added active_limit separate from recent_completed_limit in Python/Rust index query wire, updated TUI AgentLoadState with complete_visible_inbox/repair/truncation fields, routed repro/trace serialization through the new fields, and changed Tier 1 index loads to be visible-inbox complete without claiming full history. Validation: just install; just check; just rust-check.

## Dependencies

- **Blocks:** [sase-3t.2](sase-3t.2.md) ✓
- **Blocks:** [sase-3t.3](sase-3t.3.md) ✓
- **Blocks:** [sase-3t.7](sase-3t.7.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@b36766e`](https://github.com/sase-org/sase-core/commit/b36766e70387cd439dfe05dcff854c0c0bec7595) | feat: add active limit to agent index query (sase-3t.1) | [sase-3t.1](sase-3t.1.md) | 2026-05-21 14:16:48 |
| [`2e01dbd`](https://github.com/sase-org/sase/commit/2e01dbdb86f7f93e794deaf44edbe796ba774584) | feat: add visible inbox load contract (sase-3t.1) | [sase-3t.1](sase-3t.1.md) | 2026-05-21 14:21:07 |

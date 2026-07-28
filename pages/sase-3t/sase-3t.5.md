# Bead: sase-3t.5 — Phase 5 - Search And Archive Paths Are Split

[Bead Pages](../README.md) / [sase-3t](README.md) / sase-3t.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-3t.5`
**Created:** 2026-05-21 14:00:13 UTC · **Closed:** 2026-05-21 15:08:33 UTC
**Plan:** [202605/agents\_tab\_full\_refresh\_elimination.md](https://github.com/sase-org/sase--plans/blob/main/202605/agents_tab_full_refresh_elimination.md)

## Notes

COMMIT: df35e5915

[2026-07-27T18:59:27Z · sase-a1.6] [2026-05-21T15:07:13Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Implemented Phase 5 search/history split: normal sync and async Agents-tab loads now pass only the explicit full_history flag and no longer promote non-empty search queries to full history. Added focused regression coverage for active search on both load paths, while existing revive tests continue to assert explicit full-history reloads. Validation: just install; focused pytest for search split and revive reload tests; just check.

## Dependencies

- **Depends on:** [sase-3t.4](sase-3t.4.md) ✓
- **Blocks:** [sase-3t.6](sase-3t.6.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`bcb5ea7`](https://github.com/sase-org/sase/commit/bcb5ea753761cd2876e658e8966f1bbb60a8bb20) | fix: keep agent search on visible-inbox loads (sase-3t.5) | [sase-3t.5](sase-3t.5.md) | 2026-05-21 15:08:59 |

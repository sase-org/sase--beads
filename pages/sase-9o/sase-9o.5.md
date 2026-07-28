# Bead: sase-9o.5 — Repair existing ghost artifacts, bundles, and registry rows

[Bead Pages](../README.md) / [sase-9o](README.md) / sase-9o.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9o.5` · **Size:** medium
**Created:** 2026-07-25 19:11:34 UTC · **Closed:** 2026-07-26 11:29:24 UTC
**Plan:** [202607/ghost\_imported\_agents.md](https://github.com/sase-org/sase--plans/blob/main/202607/ghost_imported_agents.md)

## Description

'Phase 5 — Repair existing ghost artifacts, bundles, and registry rows' section: add an idempotent, dry-run-by-default repair command that purges already-written future-dated imported state, plus a round-trip regression test proving publish/import/re-publish converges.

## Dependencies

- **Depends on:** [sase-9o.2](sase-9o.2.md) ✓
- **Depends on:** [sase-9o.3](sase-9o.3.md) ✓
- **Depends on:** [sase-9o.4](sase-9o.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`7ae51f4`](https://github.com/sase-org/sase/commit/7ae51f46342ce4ce6cc86665d748f61f22b84734) | fix(agents): repair future-dated imported state (sase-9o.5) | [sase-9o.5](sase-9o.5.md) | 2026-07-26 11:32:17 |

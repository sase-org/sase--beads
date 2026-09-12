# Bead: sase-zu.2 — Pushdown misses degrade to deferred history, not to a blocking full scan

[Bead Pages](../README.md) / [sase-zu](README.md) / sase-zu.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.05.f0` · **Assignee:** `sase-zu.2` · **Size:** medium
**Created:** 2026-09-12 10:35:43 EDT · **Closed:** 2026-09-12 15:10:46 EDT
**Plan:** [202609/agent\_query\_load\_tiering.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_load_tiering.md)

## Description

defer: stop letting a non-window-safe committed query escalate the load tier; serve the bounded index window first, arm the existing quiet-window full-history reconcile, and show honest partial-history state.

## Notes

[2026-09-12T19:10:46Z · sase-zu.2] Implemented agents_deferred_history so pushdown misses keep bounded first paint, mark query-incomplete state, arm existing quiet-window full-history reconcile, and show the partial-history info-panel notice. Verified with focused loader/reconcile/info-panel tests, slow agent-load-tiering smoke, just _lint-symvision, just check, and sase bead epic-symbols sase-zu.2.

## Dependencies

- **Depends on:** [sase-zu.1](sase-zu.1.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zu.6](sase-zu.6.md) ◐ · ⧖ 2026-09-12
- **Blocks:** [sase-zu.7](sase-zu.7.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zu.2/README.md) | [sase-zu.2](sase-zu.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c0fd017`](https://github.com/sase-org/sase/commit/c0fd017f328fd6781da9cf5dad02922a26bf281c) | feat(agents): defer non-pushable query history loads | [sase-zu.2](sase-zu.2.md) | 2026-09-12 15:12:48 EDT |

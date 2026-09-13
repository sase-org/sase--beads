# Bead: sase-zu.8.4 — Finish query-keyed delta reuse and integrate completion with Refresh

[Bead Pages](../README.md) / [sase-zu.8](sase-zu.8.md) / sase-zu.8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zu.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zu.land.md) · **Assignee:** `sase-zu.8.4` · **Size:** medium
**Created:** 2026-09-13 10:21:17 EDT · **Closed:** 2026-09-13 14:17:16 EDT
**Plan:** [202609/agent\_query\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_landing_repairs.md)

## Description

refresh-integration: preserve exact deltas under committed queries, invalidate overflow and stale-query work, ensure settled completeness, and stamp successful Agents history completion in Refresh.

## Notes

[2026-09-13T18:17:16Z · sase-zu.8.4] Implemented query-keyed async stale-discard/retry, exact active-query deltas, delta-loss completion invalidation, and completion-time Refresh freshness stamp. Verified: epic-symbols none; ruff touched files passed; focused refresh/delta suite 65 passed with local sase-core-rs; just check reached feature-flag lint and failed on existing live flag bead sase-zx missing agents_deferred_history definition.

## Dependencies

- **Depends on:** [sase-zu.8.3](sase-zu.8.3.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-zu.8.5](sase-zu.8.5.md) ◐ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zu.8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zu.8.4/README.md) | [sase-zu.8.4](sase-zu.8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d698f92`](https://github.com/sase-org/sase/commit/d698f92e0598f5579d249579dd8d0827786e96fa) | fix(tui): preserve query-keyed agents refresh | [sase-zu.8.4](sase-zu.8.4.md) | 2026-09-13 14:18:59 EDT |

# Bead: sase-124.2 — Give the load/capacity indicator a cheap refresh path independent of broad loads

[Bead Pages](../README.md) / [sase-124](README.md) / sase-124.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mc.md) · **Assignee:** `sase-124.2` · **Size:** medium
**Created:** 2026-09-17 10:59:42 EDT · **Closed:** 2026-09-17 15:35:15 EDT
**Plan:** [202609/agents\_tab\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_freshness.md)

## Description

capacity-fresh: recompute the runner-capacity snapshot from the in-memory roster on tab entry with a guard so older in-flight loads cannot overwrite it, token-track limit-override/holds changes, and fix the stale agent-info metrics memo key.

## Notes

[2026-09-17T19:35:15Z · sase-124.2] Verified cached-roster capacity refresh, stale capacity-generation recompute, runner-limit/hold surface-token drift, and in-place agent-info metrics invalidation; focused pytest passed; full just check lint/validation stages passed, adjusted-floor full-suite run failed only suite-gate env assertions, and those tests passed without the override.

## Dependencies

- **Blocks:** [sase-124.7](sase-124.7.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.2/README.md) | [sase-124.2](sase-124.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`739caf0`](https://github.com/sase-org/sase/commit/739caf01ffd491cf3bac5589e72c221d8e1f8e56) | feat(agents): refresh runner capacity from cached roster | [sase-124.2](sase-124.2.md) | 2026-09-17 15:36:59 EDT |

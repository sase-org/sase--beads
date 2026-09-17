# Bead: sase-124.2 — Give the load/capacity indicator a cheap refresh path independent of broad loads

[Bead Pages](../README.md) / [sase-124](README.md) / sase-124.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mc.md) · **Assignee:** `sase-124.2` · **Size:** medium
**Created:** 2026-09-17 10:59:42 EDT
**Plan:** [202609/agents\_tab\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_freshness.md)

## Description

capacity-fresh: recompute the runner-capacity snapshot from the in-memory roster on tab entry with a guard so older in-flight loads cannot overwrite it, token-track limit-override/holds changes, and fix the stale agent-info metrics memo key.

## Dependencies

- **Blocks:** [sase-124.7](sase-124.7.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.2/README.md) | [sase-124.2](sase-124.2.md) | 0 |

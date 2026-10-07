# Bead: sase-1hf.4 — Resolve only live waiters from a filesystem view

[Bead Pages](../README.md) / [sase-1hf](README.md) / sase-1hf.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y0.md) · **Assignee:** `sase-1hf.4` · **Size:** medium
**Created:** 2026-10-07 14:45:46 EDT
**Plan:** [202610/wait\_lane\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_lane_repair.md)

## Description

live-waiters: shared waiting-marker walk plus tri-state runner liveness, skip dead waiters and the dependency-view build when no live waiter is pending, build the resolving view from filesystem rows instead of the slow index query, add backlog counters, and reuse the walk in sidecar_auto_sync.

## Dependencies

- **Depends on:** [sase-1hf.3](sase-1hf.3.md) ◐ · ⧖ 2026-10-07
- **Blocks:** [sase-1hf.5](sase-1hf.5.md) ◐ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1hf.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1hf.4/README.md) | [sase-1hf.4](sase-1hf.4.md) | 0 |

# Bead: sase-1bu.4 — Publishing, convergence, and honest freshness

[Bead Pages](../README.md) / [sase-1bu](README.md) / sase-1bu.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tb.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tb.w0.md) · **Assignee:** `sase-1bu.4` · **Size:** medium
**Created:** 2026-09-27 19:03:23 EDT
**Plan:** [202609/goal\_ledger.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger.md)

## Description

publish-sync: after each integration, reconcile live markers for touched goals. Mint ids only after a fetch and detect collisions. Add the unpublished outbox, a push leg on the sidecar auto-sync tick, a push-retry counter, a single-flight TTL background fetch, bounded fresh fetches, and the synced-ago watermark.

## Dependencies

- **Depends on:** [sase-1bu.3](sase-1bu.3.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bu.5](sase-1bu.5.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.4/README.md) | [sase-1bu.4](sase-1bu.4.md) | 0 |

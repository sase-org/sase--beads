# Bead: sase-zt.2 — Python adapters, launcher, and the sunset flag

[Bead Pages](../README.md) / [sase-zt](README.md) / sase-zt.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.06.f0` · **Assignee:** `sase-zt.2` · **Size:** medium
**Created:** 2026-09-12 10:33:29 EDT
**Plan:** [202609/queue\_capacity\_budget.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_budget.md)

## Description

admission: register the `queue_capacity_budget` sunset flag, pass it into the Rust entry points, rebuild against the new core revision, and carry `queue_capacity` plus the per-waiter admission limit through the adapters, the slot-poll launcher, and the agent-listing wire.

## Dependencies

- **Depends on:** [sase-zt.1](sase-zt.1.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zt.3](sase-zt.3.md) ◐ · ⧖ 2026-09-12
- **Blocks:** [sase-zt.4](sase-zt.4.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.2/README.md) | [sase-zt.2](sase-zt.2.md) | 0 |

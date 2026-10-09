# Bead: sase-1j1.1 — Single-flight, back-off, and bounded index work in FleetReadService

[Bead Pages](../README.md) / [sase-1j1](README.md) / sase-1j1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yx.md) · **Assignee:** `sase-1j1.1` · **Size:** medium
**Created:** 2026-10-09 09:31:11 EDT
**Plan:** [202610/apollo\_gateway\_snapshot\_stampede.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_gateway_snapshot_stampede.md)

## Description

gateway-single-flight: in sase-core, rewrite the FleetReadService snapshot refresh. Each scope gets one detached in-flight build that always fills the cache when it finishes. Callers wait up to the timeout. Failures back off exponentially. A shared semaphore bounds index work, the overlay pass is coalesced and best-effort, and the gateway runtime caps blocking threads. Includes a slow-build stampede regression test.

## Dependencies

- **Blocks:** [sase-1j1.4](sase-1j1.4.md) ◐ · ⧖ 2026-10-09
- **Blocks:** [sase-1j1.6](sase-1j1.6.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j1.1/README.md) | [sase-1j1.1](sase-1j1.1.md) | 0 |

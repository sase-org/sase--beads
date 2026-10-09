# Bead: sase-1j6.6 — Runner doorbell, scheduler job, and waiter safety

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.47.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.47.linker.w0.md) · **Assignee:** `sase-1j6.6` · **Size:** medium
**Created:** 2026-10-09 15:02:06 EDT
**Plan:** [202610/update\_skew\_agent\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/update_skew_agent_auto_restart.md)

## Description

trigger: have the dying runner drop a stdlib doorbell, mark recovery pending, and silence its failure notification. Add the fs-triggered scheduler job that sweeps and submits the healer as a durable proc. Keep waiters and wait_checks correct while a recovery is in flight.

## Dependencies

- **Depends on:** [sase-1j6.5](sase-1j6.5.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1j6.9](sase-1j6.9.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.6/README.md) | [sase-1j6.6](sase-1j6.6.md) | 0 |

# Bead: sase-l1.2 — Monitor start is not reported until the supervisor proves it is alive

[Bead Pages](../README.md) / [sase-l1](README.md) / sase-l1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zo](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zo.md) · **Assignee:** `sase-l1.2` · **Size:** medium
**Created:** 2026-08-13 13:38:02 EDT
**Plan:** [202608/monitor\_supervisor\_survival.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_supervisor_survival.md)

## Description

ack: have the supervisor publish a startup acknowledgement, block `start_monitor` on it, and turn a missing acknowledgement into a torn-down member and a hard `MonitorError` the still-live starter agent can act on.

## Dependencies

- **Depends on:** [sase-l1.1](sase-l1.1.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l1.6](sase-l1.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l1.2/README.md) | [sase-l1.2](sase-l1.2.md) | 0 |

# Bead: sase-ku.3 — Durable process identity for the supervisor and its child

[Bead Pages](../README.md) / [sase-ku](README.md) / sase-ku.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.3` · **Size:** small
**Created:** 2026-08-13 09:02:42 EDT
**Plan:** [202608/monitor\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_hardening.md)

## Description

identity: persist the monitored command's pgid and a boot-id/start-ticks identity for the supervisor pid before the command can outlive its recorder, scrub agent identity from the command's environment, and validate identity before signalling.

## Dependencies

- **Depends on:** [sase-ku.1](sase-ku.1.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-ku.2](sase-ku.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.4](sase-ku.4.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.3/README.md) | [sase-ku.3](sase-ku.3.md) | 0 |

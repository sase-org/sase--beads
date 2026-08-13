# Bead: sase-ku.6 — --idle-timeout for commands that hang without exiting

[Bead Pages](../README.md) / [sase-ku](README.md) / sase-ku.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.6` · **Size:** small
**Created:** 2026-08-13 09:03:03 EDT
**Plan:** [202608/monitor\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_hardening.md)

## Description

idle: add an opt-in idle timeout that fires when a monitored command has produced no output for N seconds, so `--timeout` can be generous without being useless.

## Dependencies

- **Depends on:** [sase-ku.1](sase-ku.1.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-ku.2](sase-ku.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.9](sase-ku.9.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.6/README.md) | [sase-ku.6](sase-ku.6.md) | 0 |

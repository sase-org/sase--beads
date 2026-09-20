# Bead: sase-11y.10.1.3 — Retire the AXE watchdogs and alias sase axe to sase scheduler

[Bead Pages](../README.md) / [sase-11y.10.1](sase-11y.10.1.md) / sase-11y.10.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.md) · **Assignee:** `sase-11y.10.1.3` · **Size:** large
**Created:** 2026-09-20 13:56:14 EDT
**Plan:** [202609/service\_host\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset.md)

## Description

axe-cli: delete the ensure watchdog, the opportunistic ensure on agent waits, the axe-start systemd scope wrapper and its doctor check, route the `sase update` restart through the scheduler service proc, and make `sase axe` lifecycle verbs a documented alias of `sase scheduler`.

## Dependencies

- **Depends on:** [sase-11y.10.1.2](sase-11y.10.1.2.md) ◐ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.5](sase-11y.10.1.5.md) ◐ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.6](sase-11y.10.1.6.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.3/README.md) | [sase-11y.10.1.3](sase-11y.10.1.3.md) | 0 |

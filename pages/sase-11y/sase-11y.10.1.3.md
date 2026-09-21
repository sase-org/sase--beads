# Bead: sase-11y.10.1.3 — Retire the AXE watchdogs and alias sase axe to sase scheduler

[Bead Pages](../README.md) / [sase-11y.10.1](sase-11y.10.1.md) / sase-11y.10.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.md) · **Assignee:** `sase-11y.10.1.3` · **Size:** large
**Created:** 2026-09-20 13:56:14 EDT · **Closed:** 2026-09-21 02:58:02 EDT
**Plan:** [202609/service\_host\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset.md)

## Description

axe-cli: delete the ensure watchdog, the opportunistic ensure on agent waits, the axe-start systemd scope wrapper and its doctor check, route the `sase update` restart through the scheduler service proc, and make `sase axe` lifecycle verbs a documented alias of `sase scheduler`.

## Notes

[2026-09-21T07:00:41Z · sase-11y.10.1.3.1.land] Verified by the sase-11y.10.1.3.1 land agent (auto-closed when child epic sase-11y.10.1.3.1 closed): every item in this phase's axe-cli scope is on master. The ensure watchdog, its timer, and the agent-wait heal are gone; systemd_scope.py and the axe.systemd_scope doctor check are gone; restart_after_update requests a scheduler service-proc restart; sase axe start|stop|restart|status alias sase scheduler, and both helps say so. The landing commit also retires the epic's leftover symvision symbols, the stale --force advice, and the orphaned notify_axe_restart_failed. Docs remain with sase-11y.10.1.5, which this phase blocked.

## Dependencies

- **Depends on:** [sase-11y.10.1.2](sase-11y.10.1.2.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.5](sase-11y.10.1.5.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.6](sase-11y.10.1.6.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.md) | [sase-11y.10.1.3](sase-11y.10.1.3.md) | 0 |

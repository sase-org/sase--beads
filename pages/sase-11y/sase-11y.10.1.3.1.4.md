# Bead: sase-11y.10.1.3.1.4 — Make sase axe lifecycle verbs an alias of sase scheduler

[Bead Pages](../README.md) / [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) / sase-11y.10.1.3.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.md) · **Assignee:** `sase-11y.10.1.3.1.4` · **Size:** medium
**Created:** 2026-09-20 21:17:59 EDT
**Plan:** [202609/axe\_cli\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_cli_sunset.md)

## Description

axe-alias: retarget `sase axe start|stop|restart|status` at `handle_scheduler_command`, share the scheduler parser's option builders, retarget the detached daemon command at `sase scheduler run`, and say the alias out loud in both commands' help.

## Dependencies

- **Depends on:** [sase-11y.10.1.3.1.1](sase-11y.10.1.3.1.1.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-11y.10.1.3.1.2](sase-11y.10.1.3.1.2.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-11y.10.1.3.1.3](sase-11y.10.1.3.1.3.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.3.1.5](sase-11y.10.1.3.1.5.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.3.1.4/README.md) | [sase-11y.10.1.3.1.4](sase-11y.10.1.3.1.4.md) | 0 |

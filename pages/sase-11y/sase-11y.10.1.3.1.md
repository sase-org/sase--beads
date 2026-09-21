# Bead: sase-11y.10.1.3.1 — Retire the AXE watchdogs and alias sase axe to sase scheduler

[Bead Pages](../README.md) / [sase-11y.10.1.3](sase-11y.10.1.3.md) / sase-11y.10.1.3.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.md) · **Assignee:** `sase-11y.10.1.3.1.land`
**Created:** 2026-09-20 21:17:53 EDT
**Plan:** [202609/axe\_cli\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_cli_sunset.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/axe_cli_sunset.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/axe_cli_sunset.md

<!-- sase:links:end -->

## Description

The sase service host is the only thing that starts, restarts, or stops the scheduler from a CLI path: the ensure watchdog and its systemd timer are gone, no agent wait heals axe, the axe-start systemd scope wrapper and its doctor check are gone, `sase update` / `sase flag` / `sase plugin` restart the `scheduler` service proc instead of the AXE daemon, `sase axe start|stop|restart|status` is a documented alias of `sase scheduler`, and the direct AXE restart machinery that those paths kept alive is deleted.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.3.1.land/README.md) | [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) | 0 |

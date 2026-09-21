# Bead: sase-11y.10 — Sunset legacy paths, docs, and glossary

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m3.md) · **Assignee:** `sase-11y.10` · **Size:** large
**Created:** 2026-09-16 14:42:07 EDT · **Closed:** 2026-09-21 06:37:37 EDT
**Plan:** [202609/service\_host\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_1.md)

## Description

sunset: retire the ensure timer, TUI direct-start, and scope-wrapper paths, formalize the sase axe alias, canonicalize the services tab id, remove the service_host beta flag, update docs, and land the new and edited glossary strands via the memory-write skill.

## Notes

[2026-09-21T10:42:02Z · sase-11y.10.1.7.land] Phase verified complete by sase-11y.10.1.7.land. The bead store auto-closed this phase ('delegated work landed') when its child epic sase-11y.10.1 closed. Each item this phase required is shipped in source:
- the ensure timer/watchdog is retired (`sase axe ensure` is rejected on master; sase-axe-ensure units are only LEGACY_SYSTEMD_UNITS cleanup targets);
- the TUI direct-start path, the axe-start scope wrapper, the sase-update direct restart, and the chat-install direct start (sase-152) are gone. start_axe_daemon has no references left.
- `sase axe start|stop|restart|status` is a documented alias of `sase scheduler`;
- the tab id is services;
- the service_host beta flag and its Off branches are removed;
- the docs describe the service host, the scheduler alias, and the Services tab;
- the glossary strands landed.
See the close notes on sase-11y.10.1 and sase-11y.10.1.7. The containing epic sase-11y is left to its land agent. A DISCOVERED ISSUE note was recorded on sase-11y for the stale `proc show`/`scheduler status` state.

## Dependencies

- **Depends on:** [sase-11y.7](sase-11y.7.md) ✓ · ⧖ 2026-09-16
- **Depends on:** [sase-11y.8](sase-11y.8.md) ✓ · ⧖ 2026-09-16
- **Depends on:** [sase-11y.9](sase-11y.9.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.md) | [sase-11y.10](sase-11y.10.md) | 0 |

# Bead: sase-11y.10.1.2 — Remove the service\_host beta flag and its Off branches

[Bead Pages](../README.md) / [sase-11y.10.1](sase-11y.10.1.md) / sase-11y.10.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.md) · **Assignee:** `sase-11y.10.1.2` · **Size:** large
**Created:** 2026-09-20 13:56:13 EDT
**Plan:** [202609/service\_host\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset.md)

## Description

flag-removal: delete the `service_host` registry entry and every gate that reads it, delete the Off branches in the scheduler handler, the TUI, the mobile gateway, doctor, init, and the service control plane, make the On branch unconditional, and close flag bead sase-12m.

## Dependencies

- **Depends on:** [sase-11y.10.1.1](sase-11y.10.1.1.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.3](sase-11y.10.1.3.md) ◐ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.4](sase-11y.10.1.4.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.2/README.md) | [sase-11y.10.1.2](sase-11y.10.1.2.md) | 0 |

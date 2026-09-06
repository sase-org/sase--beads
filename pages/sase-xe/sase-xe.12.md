# Bead: sase-xe.12 — The %dispatch directive and reliable remote launch

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.12

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.12` · **Size:** large
**Created:** 2026-09-06 14:06:47 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

dispatch-launch: add %dispatch:<machine> to the dual-sourced directive vocabulary, intercept routing in the shared launch trunk before any target-side allocation, persist source intent with an operation key, send a portable launch request validated and admitted on the target, bind the receipt, auto-follow the resulting family, and reconcile lost replies without ever falling back to another machine.

## Dependencies

- **Depends on:** [sase-xe.10](sase-xe.10.md) ◐ · ⧖ 2026-09-06
- **Blocks:** [sase-xe.13](sase-xe.13.md) ◐ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.6](sase-xe.6.md) ◐ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.8](sase-xe.8.md) ◐ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.12/README.md) | [sase-xe.12](sase-xe.12.md) | 0 |

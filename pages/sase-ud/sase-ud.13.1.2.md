# Bead: sase-ud.13.1.2 — Remove the gate\_shell\_handoff flag and the blocking Off branch

[Bead Pages](../README.md) / [sase-ud.13.1](sase-ud.13.1.md) / sase-ud.13.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.md) · **Assignee:** `sase-ud.13.1.2` · **Size:** large
**Created:** 2026-08-27 08:49:05 EDT
**Plan:** [202608/gate\_shell\_status\_collapse.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shell_status_collapse.md)

## Description

flag-removal: make the gate-shell handoff unconditional in the plan and questions marker handlers, delete the flag module, registry member, and config schema property, delete the blocking wait machinery the Off branch was the last consumer of, retarget the runner tests that drove the Off branch, and close flag bead sase-uo.

## Dependencies

- **Blocks:** [sase-ud.13.1.3](sase-ud.13.1.3.md) ◐ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.1.2.md) | [sase-ud.13.1.2](sase-ud.13.1.2.md) | 0 |

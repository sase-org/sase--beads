# Bead: sase-l1.1 — Supervisor survives its starter's teardown

[Bead Pages](../README.md) / [sase-l1](README.md) / sase-l1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zo](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zo.md) · **Assignee:** `sase-l1.1` · **Size:** medium
**Created:** 2026-08-13 13:37:39 EDT
**Plan:** plan:202608/monitor\_supervisor\_survival.md

## Description

detach: reparent the supervisor to PID 1 before `start_monitor` returns and set its signal dispositions in the first statements it executes, so the starter's runner teardown cannot kill it during its startup window.

## Dependencies

- **Blocks:** [sase-l1.2](sase-l1.2.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-l1.6](sase-l1.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l1.1/README.md) | [sase-l1.1](sase-l1.1.md) | 0 |

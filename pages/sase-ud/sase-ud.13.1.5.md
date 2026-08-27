# Bead: sase-ud.13.1.5 — One nested family\_shell wire record at schema v7

[Bead Pages](../README.md) / [sase-ud.13.1](sase-ud.13.1.md) / sase-ud.13.1.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.md) · **Assignee:** `sase-ud.13.1.5` · **Size:** medium
**Created:** 2026-08-27 08:49:08 EDT
**Plan:** [202608/gate\_shell\_status\_collapse.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shell_status_collapse.md)

## Description

wire-v7: fold the flat `monitor_*` and `gate_*` field blocks on `AgentMetaWire` and `DoneMarkerWire` into one nested `family_shell` record in both the Rust core and the Python wire, bump the agent-scan wire schema to 7, and keep every existing reader working through a compatibility projection.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ud.13.1.5/README.md) | [sase-ud.13.1.5](sase-ud.13.1.5.md) | 0 |

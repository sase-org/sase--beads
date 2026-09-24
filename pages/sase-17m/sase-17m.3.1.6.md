# Bead: sase-17m.3.1.6 — Agent name registry session kinds and schema v3

[Bead Pages](../README.md) / [sase-17m.3.1](sase-17m.3.1.md) / sase-17m.3.1.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) · **Assignee:** `sase-17m.3.1.6` · **Size:** small
**Created:** 2026-09-24 02:56:50 EDT
**Plan:** [202609/agent\_session\_wire\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_wire_cutover.md)

## Description

name-registry: agent_name_registry.json reservation_kind and container_kind become session, readers accept family, and SCHEMA_VERSION goes 2 to 3 through the existing legacy-upgrade and stale-cache rebuild path without moving a rebuild onto ACE startup or the UI thread.

## Dependencies

- **Depends on:** [sase-17m.3.1.4](sase-17m.3.1.4.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.3.1.7](sase-17m.3.1.7.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.6/README.md) | [sase-17m.3.1.6](sase-17m.3.1.6.md) | 0 |

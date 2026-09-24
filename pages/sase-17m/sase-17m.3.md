# Bead: sase-17m.3 — Python persistence and wire cutover

[Bead Pages](../README.md) / [sase-17m](README.md) / sase-17m.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qh.md) · **Assignee:** `sase-17m.3` · **Size:** large
**Created:** 2026-09-23 22:46:36 EDT
**Plan:** [202609/agent\_session\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_rename.md)

## Description

wire-cutover: bump the core pin and switch sase to the new binding names. Rename the Python wire mirrors and durable JSON fields: new data is written only with agent_session keys, and readers accept both key spellings. Rename the Agent model fields and the rebuildable caches.

## Dependencies

- **Depends on:** [sase-17m.1](sase-17m.1.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-17m.2](sase-17m.2.md) ◐ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.4](sase-17m.4.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3/README.md) | [sase-17m.3](sase-17m.3.md) | 0 |

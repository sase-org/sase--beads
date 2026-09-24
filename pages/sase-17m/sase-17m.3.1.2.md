# Bead: sase-17m.3.1.2 — Canonical agent-session metadata keys and shared accessor

[Bead Pages](../README.md) / [sase-17m.3.1](sase-17m.3.1.md) / sase-17m.3.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) · **Assignee:** `sase-17m.3.1.2` · **Size:** medium
**Created:** 2026-09-24 02:56:45 EDT
**Plan:** [202609/agent\_session\_wire\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_wire_cutover.md)

## Description

canonical-keys: make src/sase/plan_chain.py own AGENT_SESSION_* keys, the separator, and LEGACY_AGENT_FAMILY_* constants read only by one shared accessor. Route every agent_meta.json / done.json reader through it and make every writer emit only agent_session, agent_session_role, and agent_session_shell, dropping legacy keys on rewrite.

## Dependencies

- **Depends on:** [sase-17m.3.1.1](sase-17m.3.1.1.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.3.1.3](sase-17m.3.1.3.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.2/README.md) | [sase-17m.3.1.2](sase-17m.3.1.2.md) | 0 |

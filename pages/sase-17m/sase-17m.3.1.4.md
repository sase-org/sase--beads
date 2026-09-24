# Bead: sase-17m.3.1.4 — Agent model fields

[Bead Pages](../README.md) / [sase-17m.3.1](sase-17m.3.1.md) / sase-17m.3.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) · **Assignee:** `sase-17m.3.1.4` · **Size:** medium
**Created:** 2026-09-24 02:56:47 EDT
**Plan:** [202609/agent\_session\_wire\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_wire_cutover.md)

## Description

agent-model: rename the family-concept fields of the Agent dataclass (src/sase/ace/tui/models/_agent_state.py) to agent_session* and update every src and tests reference mechanically, keeping ACE module, label, and row names for ace-cutover. Dismissed agent bundles still load the old field names.

## Dependencies

- **Depends on:** [sase-17m.3.1.3](sase-17m.3.1.3.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.3.1.5](sase-17m.3.1.5.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.3.1.6](sase-17m.3.1.6.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.4/README.md) | [sase-17m.3.1.4](sase-17m.3.1.4.md) | 0 |

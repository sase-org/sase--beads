# Bead: sase-17m.3.1 — Python persistence and wire cutover to agent session (wire-cutover)

[Bead Pages](../README.md) / [sase-17m.3](sase-17m.3.md) / sase-17m.3.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) · **Assignee:** `sase-17m.3.1.land`
**Created:** 2026-09-24 02:56:43 EDT
**Plan:** [202609/agent\_session\_wire\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_wire_cutover.md)

## Description

sase is pinned to the landed core-expand sase-core commit, calls only the new agent-session binding names, and names the former agent-family concept "agent session" in its canonical metadata keys, Python wire mirrors, Agent model fields, durable Python-owned JSON, and the agent name registry. New data is written only with agent-session keys and values, every reader still loads pre-rename data through named legacy helpers, and `sase tool run check` passes.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.land/README.md) | [sase-17m.3.1](sase-17m.3.1.md) | 0 |

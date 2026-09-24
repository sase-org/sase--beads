# Bead: sase-17m.3.1.1 — Core pin bump and new binding names

[Bead Pages](../README.md) / [sase-17m.3.1](sase-17m.3.1.md) / sase-17m.3.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) · **Assignee:** `sase-17m.3.1.1` · **Size:** medium
**Created:** 2026-09-24 02:56:44 EDT
**Plan:** [202609/agent\_session\_wire\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_wire_cutover.md)

## Description

pin-bindings: ratchet sase-core-revision.txt to the landed core-expand commit, switch every caller to parse_agent_session_name, resolve_agent_session_parent, reconcile_agent_artifact_index_dismissed_agent_session_members, and fleet_followed_batch_agent_session_promotions, rename the Python facade wrappers for them, update tools/validate_sase_core_rs and the demo seed, and tighten the dual-shape directive tests to session-only.

## Dependencies

- **Blocks:** [sase-17m.3.1.2](sase-17m.3.1.2.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.1/README.md) | [sase-17m.3.1.1](sase-17m.3.1.1.md) | 0 |

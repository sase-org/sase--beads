# Bead: sase-17m.5.1.1 — ACE model modules and Agent identifiers

[Bead Pages](../README.md) / [sase-17m.5.1](sase-17m.5.1.md) / sase-17m.5.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.md) · **Assignee:** `sase-17m.5.1.1` · **Size:** medium
**Created:** 2026-09-25 00:06:02 EDT
**Plan:** [202609/agent\_session\_ace\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover.md)

## Description

models: rename the family-named modules in src/sase/ace/tui/models/ (_agent_imported_family, _agent_parallel_family, _agent_status_family{,_core,_planner,_policy}, _family_shell_membership, agent_family_members, agent_family_preview_cache). Also rename their classes and functions, the family-concept Agent methods and properties (is_family_member_child, family_reference_name, presented_family_reference_name), AgentChildLinkage.FAMILY_MEMBER, and the family identifiers in agent_groups, agent_tribe_summary, agent_nodes, agent_bundle, clan, loaders, and fleet-agents models. Core-emitted legacy keys stay as marked readers. Update every importer, in or outside ACE, and rename the matching tests/ace/tui/models tests and helpers.

## Dependencies

- **Blocks:** [sase-17m.5.1.2](sase-17m.5.1.2.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.1/README.md) | [sase-17m.5.1.1](sase-17m.5.1.1.md) | 0 |

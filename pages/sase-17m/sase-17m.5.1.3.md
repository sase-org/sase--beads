# Bead: sase-17m.5.1.3 — Artifacts-pane contract, row kinds, and completion kinds

[Bead Pages](../README.md) / [sase-17m.5.1](sase-17m.5.1.md) / sase-17m.5.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.md) · **Assignee:** `sase-17m.5.1.3` · **Size:** medium
**Created:** 2026-09-25 00:06:04 EDT
**Plan:** [202609/agent\_session\_ace\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover.md)

## Description

contract-completion: rename the Agents-pane relation family/agent_family_container to session/agent_session_container, the grouping mode by_family (label Family, keys family) to by_session (label Session), and _artifact_tab_model FAMILY. Keep the Patch RelationKind.FAMILY. Rename the row kinds and identifiers in widgets/artifacts (agents_list, agents_navigation, agents_revival, query_rows) and relations/agents.py. Change the agent completion candidate kind "family" to "session" across the completion models, directive completion, and the prompt-bar completion rows. Update the artifacts contract goldens and the completion parity tests.

## Dependencies

- **Depends on:** [sase-17m.5.1.2](sase-17m.5.1.2.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-17m.5.1.4](sase-17m.5.1.4.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.3/README.md) | [sase-17m.5.1.3](sase-17m.5.1.3.md) | 0 |

# Bead: sase-1jm.4.1.3 — Lifecycle and Provenance cards for both views

[Bead Pages](../README.md) / [sase-1jm.4.1](sase-1jm.4.1.md) / sase-1jm.4.1.3

**Status:** ○ open · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [sase-1jm.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4/README.md) · **Size:** medium
**Created:** 2026-10-11 05:30:38 EDT
**Plan:** [202610/agents\_archive\_view\_record\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_record_deck.md)

## Description

record-facts: build the Lifecycle card (@agent: reference, Inbox or Archive location, status and outcome, started/ended/dismissed times with time basis, revived xN, capabilities with missing requirements) and the Provenance card (project, workspace, model, provider and effort, agent tab, tribe, clan tribe, owner, source run id, chat path, artifacts dir, bundle path when archived) in a new src/sase/ace/tui/widgets/decks/record_facts.py module (disjoint from the relations phase). Use existing Agent fields for inbox agents and the sase-1jm.2 archive-projection derivation (src/sase/core/agent_archive_facade.py capabilities and corpus summary) for archived agents; never add a parallel status table. Honor the epic DECISIONS: edit no memory notes. Test card content for an inbox agent, an archived agent, a container, and a thin agent with no artifacts dir.

## Dependencies

- **Depends on:** [sase-1jm.4.1.1](sase-1jm.4.1.1.md) ○ · ⧖ 2026-10-11
- **Blocks:** [sase-1jm.4.1.5](sase-1jm.4.1.5.md) ○ · ⧖ 2026-10-11

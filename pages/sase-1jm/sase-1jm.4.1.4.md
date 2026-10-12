# Bead: sase-1jm.4.1.4 — Relations and Links cards with off-thread link facets

[Bead Pages](../README.md) / [sase-1jm.4.1](sase-1jm.4.1.md) / sase-1jm.4.1.4

**Status:** ✓ closed · **Resolution:** superseded · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [sase-1jm.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4/README.md) · **Size:** medium
**Created:** 2026-10-11 05:30:47 EDT · **Closed:** 2026-10-12 06:52:41 EDT
**Plan:** [202610/agents\_archive\_view\_record\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_record_deck.md)

## Description

record-relations: build the Relations card (session, clan, parent, workflow parent, retry_of/retried_as as copyable references; interactive jumps stay in the Jump panel, no jump behavior changes) and the Links card (incoming and outgoing artifact links grouped by relation) in a new src/sase/ace/tui/widgets/decks/record_relations.py module (disjoint from the facts phase), reusing the cached load_artifact_links_snapshot (src/sase/ace/tui/relations/artifact_links.py) off-thread. Carry over the facts the retiring pane holds (src/sase/ace/tui/widgets/artifacts/agents_detail_panel.py and agents_detail.py) without touching the pane itself. Never call catalog-sized facet paths on ticks; revalidate on signature drift only. Honor the epic DECISIONS: edit no memory notes. Test card content for an agent with links and an agent with none.

## Dependencies

- **Depends on:** [sase-1jm.4.1.1](sase-1jm.4.1.1.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jm.4.1.5](sase-1jm.4.1.5.md) ✓ · ⧖ 2026-10-11

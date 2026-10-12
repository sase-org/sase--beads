# Bead: sase-1jm.4.1.1 — RECORD deck registry, cycle order, and persistence

[Bead Pages](../README.md) / [sase-1jm.4.1](sase-1jm.4.1.md) / sase-1jm.4.1.1

**Status:** ✓ closed · **Resolution:** superseded · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [sase-1jm.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4/README.md) · **Size:** small
**Created:** 2026-10-11 05:30:23 EDT · **Closed:** 2026-10-12 06:52:41 EDT
**Plan:** [202610/agents\_archive\_view\_record\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_record_deck.md)

## Description

record-registry: add DeckId.RECORD to src/sase/ace/tui/widgets/decks/model.py and its _DeckSpec to widgets/decks/spec.py (name RECORD, glyph ≡, picker key r, accent #87AFAF, blurb "Lifecycle, provenance, relations, links"). Place Record last in DECK_CYCLE and active_deck_cycle. Extend src/sase/ace/tui/models/agent_deck_persistence.py so states without Record still round-trip and unknown decks keep their tolerant fallback. Choose the Record card-builder module names and probe name once and record them on this bead. Unit-test the spec entry, cycle order, coercion, and persistence round-trip.

## Dependencies

- **Blocks:** [sase-1jm.4.1.2](sase-1jm.4.1.2.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jm.4.1.3](sase-1jm.4.1.3.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jm.4.1.4](sase-1jm.4.1.4.md) ✓ · ⧖ 2026-10-11

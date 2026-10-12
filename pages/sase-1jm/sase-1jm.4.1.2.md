# Bead: sase-1jm.4.1.2 — Record panel compose, picker, availability, and keys

[Bead Pages](../README.md) / [sase-1jm.4.1](sase-1jm.4.1.md) / sase-1jm.4.1.2

**Status:** ✓ closed · **Resolution:** superseded · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [sase-1jm.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4/README.md) · **Size:** medium
**Created:** 2026-10-11 05:30:30 EDT · **Closed:** 2026-10-12 06:52:41 EDT
**Plan:** [202610/agents\_archive\_view\_record\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_record_deck.md)

## Description

record-chrome: wire RECORD through DeckPanel compose (src/sase/ace/tui/widgets/decks/panel.py), titles, the deck picker modal (fifth RECORD row with glyph ≡ and key r), src/sase/ace/tui/widgets/decks/availability.py (a probe that always reports at least one card), deck cycling, src/sase/default_config.yml, the keymap registries, the ? help modal Agents section, and footer metadata. Use the builder/probe contracts recorded on sase-1jm.4.1.1. Resolve the exact cycle keys against the keymaps (cycle_deck_view and Ctrl+J/Ctrl+K); do not invent bindings. Honor the epic DECISIONS: edit no memory notes. Test the picker row, picker key, and always-available probe.

## Dependencies

- **Depends on:** [sase-1jm.4.1.1](sase-1jm.4.1.1.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jm.4.1.5](sase-1jm.4.1.5.md) ✓ · ⧖ 2026-10-11

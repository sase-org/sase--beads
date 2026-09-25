# Bead: sase-17d.4 — Card and deck cycling keys

[Bead Pages](../README.md) / [sase-17d](README.md) / sase-17d.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qd.md) · **Assignee:** `sase-17d.4` · **Size:** medium
**Created:** 2026-09-23 19:16:50 EDT · **Closed:** 2026-09-23 21:57:13 EDT
**Plan:** [202609/agents\_tab\_decks\_and\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_decks_and_cards.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-193][1] | The phase bead that closed done while its work never committed |

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-193/README.md

<!-- sase:links:end -->

## Description

deck-navigation-keys: Ctrl+J/K cycle cards and Ctrl+N/P cycle decks in the focused panel, with sticky preferred cards. Ctrl+D/U, g/G and the bottom pin target the focused deck panel. Includes full keymap registration and the first flag-on PNG goldens.

## Notes

[2026-09-24T01:56:35Z · sase-17d.4] PROPOSED FOLLOW-UP: just check symvision gate fails on clean HEAD with 73 private-import violations (usage/doctor/fakey/plug-browser files); needs a sweep by the owning bead

[2026-09-24T01:57:13Z · sase-17d.4] deck-navigation-keys done: Ctrl+J/K cycle cards (sticky preferred) and Ctrl+N/P cycle decks in focused panel via 4 new keymapped actions; Ctrl+D/U, g/G, Ctrl+F/B and bottom pin retarget to focused deck panel; empty-state shows live deck-switch hint; 2 flag-on PNG goldens. Verified: 51 deck tests, 240 catalog/keymap tests, 160 nav/availability/help tests, 1 visual test pass; sase tool run check green except pre-existing symvision failure (identical 73 errors on clean HEAD). One-line mypy drive-by in file_panel/_content.py (getattr parent).

## Dependencies

- **Depends on:** [sase-17d.3](sase-17d.3.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17d.5](sase-17d.5.md) ✓ · ⧖ 2026-09-23

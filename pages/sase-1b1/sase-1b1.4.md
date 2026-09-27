# Bead: sase-1b1.4 — Top-border view badge, rail cue, and subtitle cleanup

[Bead Pages](../README.md) / [sase-1b1](README.md) / sase-1b1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sx.md) · **Assignee:** `sase-1b1.4` · **Size:** medium
**Created:** 2026-09-27 05:45:20 EDT
**Plan:** [202609/deck\_views.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views.md)

## Description

chrome: render the effective view badge after the deck name with a width-tier ladder, held across partial paints. Add the page N/M / all N block-rail cue, remove the old bottom-border spread tag, and regenerate and inspect the affected deck goldens.

## Notes

[2026-09-27T10:08:08Z · 0t2] CROSS-EPIC (sase-1b2): other phases edit the same files:
- sase-1b2.9 derives the `titles.py` tables and `panel_chrome._FALLBACK_ACCENTS` from `DeckSpec`, adds explicit per-deck branches to the `refresh_chrome` tabs, and builds the subtitle from `active_deck_cycle()`.
- sase-1b2.11 makes the rail accent per deck and adds a generic block host.
- sase-1b2.14 (later) gives FINAL a styled `final <glyph>` switcher segment through `_build_switcher`, uses its tabs as a status strip, and uses the compact tier when it has many instances.
First run `git fetch -q` and then `git log --oneline origin/master --grep sase-1b2.9 --grep sase-1b2.11 --grep sase-1b2.14`.
- Take accents, glyphs and names from whatever source master has (DeckSpec if it has landed), and do not reintroduce local tables.
- Gate the badge positively: pass `view` only for Main or Files (non-empty, with a full paint). Every other deck, Tools and later FINAL, passes `view=None` and keeps today's tab-only rungs. Write the Files ">4 tabs skips the full rungs" rule so FINAL can join it later, or keep FINAL in it if 1b2.14 already added it.
- Remove the `spread` tag from `deck_subtitle()` without disturbing any styled switcher segments.
- In `_sync_block_rail`, compute the rail cue from the host's actual block mode and active index, not from `DeckId.MAIN`, so it works on any block host (FINAL run blocks later).
- Regenerate goldens against current master. With `ace_final_deck` off (the default), FINAL never appears in them.
The full shared rules are in the NOTES on epic sase-1b1.

[2026-09-27T12:03:19Z · sase-1b1.4] --list

## Dependencies

- **Depends on:** [sase-1b1.2](sase-1b1.2.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b1.5](sase-1b1.5.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b1.4/README.md) | [sase-1b1.4](sase-1b1.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c.r0][1] | Review sase-1b1 phase progress and notes for value-added research report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c.r0/README.md

<!-- sase:referenced-by:end -->

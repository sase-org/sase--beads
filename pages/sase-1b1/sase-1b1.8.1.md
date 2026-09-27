# Bead: sase-1b1.8.1 — Re-apply the sase-1b1 landing integration fixes

[Bead Pages](../README.md) / [sase-1b1.8](sase-1b1.8.md) / sase-1b1.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1b1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.land.md) · **Assignee:** `sase-1b1.8.1` · **Size:** small
**Created:** 2026-09-27 14:53:03 EDT · **Closed:** 2026-09-27 15:14:21 EDT
**Plan:** [202609/deck\_views\_landing\_remainder.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views_landing_remainder.md)

## Description

integrate: move four keymap tests that remap actions onto the now-owned P key to the free key B. Privatize three view_policy symbols flagged by symvision. Make DeckViewPolicies.with_deck and distinct layouts dispatch explicitly on Main/Files. Delete the shadowed card_documents view_policy duplicate and add the R4 FINAL-panel persistence test.

## Notes

[2026-09-27T19:02:27Z · sase-1b1.8.1] PROPOSED FOLLOW-UP: pre-existing master-red failures reproduce identically on clean tree — test_card_document_decks_is_main_only and test_picker_catalog_covers_every_deck (FINAL-deck, tracked for sase-1b2) plus just symvision usage_windows.py telegram-pragma reds (4 errors, no view_policy.py entry)

[2026-09-27T19:14:01Z · sase-1b1.8.1--1] PROPOSED FOLLOW-UP: verified clean-tree reproduction 2026-09-27 — same 4 usage_windows.py telegram-pragma symvision errors and test_card_document_decks_is_main_only fail with phase changes stashed (tracked for sase-1b2 per prior note)

[2026-09-27T19:14:21Z · sase-1b1.8.1--1] Phase scope done (P->B keymap moves, view_policy privatization + Main/Files dispatch, card_documents duplicate removal, R4 FINAL persistence test). Verified: 146/147 phase tests pass; the 1 failure (test_card_document_decks_is_main_only) and 4 usage_windows.py symvision telegram-pragma errors reproduce identically on clean stashed tree, so pre-existing per prior follow-up note. No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1b1.8.3](sase-1b1.8.3.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.8.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.8.1.md) | [sase-1b1.8.1](sase-1b1.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`67c43d5`](https://github.com/sase-org/sase/commit/67c43d5746db2412d88ca57d4860d00239699a09) | feat(decks): re-apply sase-1b1 landing integration fixes (sase-1b1.8.1) | [sase-1b1.8.1](sase-1b1.8.1.md) | 2026-09-27 15:23:50 EDT |

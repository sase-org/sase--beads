# Bead: sase-1bn.1 — Three sidebar modes and the zoom state fixes

[Bead Pages](../README.md) / [sase-1bn](README.md) / sase-1bn.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.2h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2h.md) · **Assignee:** `sase-1bn.1` · **Size:** medium
**Created:** 2026-09-27 17:33:12 EDT · **Closed:** 2026-09-27 18:39:44 EDT
**Plan:** [202609/agents\_node\_rail\_and\_zoom.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_rail_and_zoom.md)

## Description

sidebar-modes: derive EXPANDED / RAIL / HIDDEN from deck-area state. Stop zoom from writing nodes_collapsed, and make Ctrl+S while zoomed restore the snapshot like Z. Route every deck-state change through one sync choke point, un-nest the info-row zoom chip, and update the tests, docs, and zoom goldens.

## Notes

[2026-09-27T22:39:01Z · sase-1bn.1--2] PROPOSED FOLLOW-UP: stale test_final_panel_decoded_to_main_keeps_views fails on clean base — commit 2d8f2f056 removed ace_final_deck flag and the final->main decode fallback but left the test expecting DeckId.MAIN; fix by updating or deleting the test

[2026-09-27T22:39:19Z · sase-1bn.1--2] PROPOSED FOLLOW-UP: just check lint-symvision fails on clean base — panel_view_deferred.build_prebuilt_offthread imports private _segment_section_identity from prompt_panel._section_navigation; fix by making it public

[2026-09-27T22:39:44Z · sase-1bn.1--2] sidebar-modes done: EXPANDED/RAIL/HIDDEN derived from deck-area state, zoom no longer writes nodes_collapsed, Ctrl+S while zoomed restores snapshot, single sync choke point, un-nested zoom chip. Verified: 3 zoom goldens regenerated and their snapshot tests pass (pixel diffs vs old goldens 2.6-5.3 pct, localized spine removal); focused unit lanes 79 passed; epic-symbols clean. Two failures reproduce identically on clean base and are recorded as PROPOSED FOLLOW-UPs: stale test_final_panel_decoded_to_main_keeps_views (flag-removal commit 2d8f2f056 orphaned it) and lint-symvision private-import of _segment_section_identity.

## Dependencies

- **Blocks:** [sase-1bn.4](sase-1bn.4.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1bn.5](sase-1bn.5.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bn.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bn.1.md) | [sase-1bn.1](sase-1bn.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`42bb50a`](https://github.com/sase-org/sase/commit/42bb50a80c7a5d25e3d8e49e4a2279ba775b120f) | feat(ace): three sidebar modes with zoom state fixes (sase-1bn.1) | [sase-1bn.1](sase-1bn.1.md) | 2026-09-27 18:42:27 EDT |

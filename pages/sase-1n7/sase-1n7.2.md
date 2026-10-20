# Bead: sase-1n7.2 — Lock-toggle key and lock copy

[Bead Pages](../README.md) / [sase-1n7](README.md) / sase-1n7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.52.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.52.linker.w0.md) · **Assignee:** `sase-1n7.2` · **Size:** medium
**Created:** 2026-10-19 17:08:02 EDT · **Closed:** 2026-10-19 20:47:04 EDT
**Plan:** [202610/deck\_scroll\_scope.md](https://github.com/sase-org/sase--plans/blob/main/202610/deck_scroll_scope.md)

## Description

lock-key: an Agents-only action that locks the layout auto chose or returns to automatic, wired through keymaps, availability, palette, footer, help, the first-lock toast, and generated keymap docs.

## Notes

[2026-10-20T00:46:18Z · sase-1n7.2--2] PROPOSED FOLLOW-UP: Fix sticky Reply landing in the narrow spread deck visual case — test_agents_deck_blocks_spread_deck_sticky_png_snapshot times out waiting for spread_active_card() == reply on both the changed tree and a clean HEAD checkout; the skipped golden remains unchanged.

[2026-10-20T00:47:04Z · sase-1n7.2--2] Implemented Agents deck view lock toggle on Shift+B with availability, palette, footer, first-lock toast, help, default config, and generated keymap docs; just fix and sase tool run check passed. Reviewed the targeted snapshot report and all 23 updated goldens; one sticky Reply snapshot remains skipped after the same state timeout also reproduced on clean HEAD and is recorded as a proposed follow-up. epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-1n7.1](sase-1n7.1.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n7.3](sase-1n7.3.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n7.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n7.2.md) | [sase-1n7.2](sase-1n7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`798e786`](https://github.com/sase-org/sase/commit/798e786c88c01c265748f294cc7af700d0099b3f) | feat(ace): add Agents deck view lock toggle | [sase-1n7.2](sase-1n7.2.md) | 2026-10-19 20:48:05 EDT |

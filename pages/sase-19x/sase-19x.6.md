# Bead: sase-19x.6 — Block-spread and deck-spread block navigation and transitions

[Bead Pages](../README.md) / [sase-19x](README.md) / sase-19x.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s4.md) · **Assignee:** `sase-19x.6` · **Size:** medium
**Created:** 2026-09-25 20:37:46 EDT · **Closed:** 2026-09-26 08:22:52 EDT
**Plan:** [202609/agent\_data\_card\_blocks.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_data_card_blocks.md)

## Description

block-spread-view: add chat-log newest landing and anchor-motion navigation for block-spread cards and spread decks, the scroll-derived block cursor, and a block-aware layout reserve. Replace the ad hoc spread/paged anchoring with one hierarchical ReadingAnchor capture/restore that also covers block-mode transitions.

## Notes

[2026-09-26T12:22:30Z · sase-19x.6] PROPOSED FOLLOW-UP: Remove stale symvision --epic-symbol entries for closed bead sase-19x.4 (phase_card_block, block_meta_for_session_shell, session_reply_heading); just _lint-symvision reports bead is closed on both base and this branch

[2026-09-26T12:22:52Z · sase-19x.6] block-spread-view done: ReadingAnchor in panel_transitions.py with deck/block spread-paged capture/restore (block_id=None reproduces prior math), block-aware reserve include_blocks, chat-log landing min(header,real_bottom) with deferred retry, spread [/] anchor-motion with unknown-anchor wrap, scroll-derived cursor via derive_spread_block/select_cursor (same-block preserves arrivals), deck-spread sticky-Reply landing and following re-land; verified 8 new spread pilots + 14 paged pilots + 13 spread pilots green, ruff and mypy clean, consumed symvision cycle_block_id/derive_spread_block/land_cursor

## Dependencies

- **Depends on:** [sase-19x.5](sase-19x.5.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-19x.8](sase-19x.8.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19x.6/README.md) | [sase-19x.6](sase-19x.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5f082a5`](https://github.com/sase-org/sase/commit/5f082a5f13c84b5128d51992ff1696d1815a9c0d) | feat(ace-tui): block-spread and deck-spread navigation with ReadingAnchor (sase-19x.6) | [sase-19x.6](sase-19x.6.md) | 2026-09-26 08:24:34 EDT |

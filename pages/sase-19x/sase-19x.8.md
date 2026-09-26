# Bead: sase-19x.8 — The one-row block rail

[Bead Pages](../README.md) / [sase-19x](README.md) / sase-19x.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s4.md) · **Assignee:** `sase-19x.8` · **Size:** medium
**Created:** 2026-09-25 20:37:50 EDT · **Closed:** 2026-09-26 09:20:07 EDT
**Plan:** [202609/agent\_data\_card\_blocks.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_data_card_blocks.md)

## Description

block-rail: add the pure tiered block_rail_text renderer and the pre-composed BlockRail widget, docked under the Main deck panel's top border. It uses roster numbers, glyphs and status colors, an accent pill for the active block, arrival dots, a key hint at the widest tier, click-to-select, focus dimming and theme updates.

## Notes

[2026-09-26T12:51:32Z · sase-19x.8] PROPOSED FOLLOW-UP: Capture SASE_FEATURE_FLAGS={"card_blocks": true} sase screenshot PNGs (single panel + LEFT_RIGHT split, compact/unfocused tiers) and verify the pill caps render cleanly in the bundled font, else fall back to a space-padded pill

[2026-09-26T12:52:18Z · sase-19x.8] PROPOSED FOLLOW-UP: just toobig reports src/sase/tool/executor.py at 1168 lines (limit 1000); pre-existing on the clean base tree, untouched by the block-rail phase

[2026-09-26T13:19:49Z · sase-19x.8--1] PROPOSED FOLLOW-UP: just check is red on the clean base tree (verified via git stash): tests/test_axe_lumberjack_config.py fails with axe_config_unknown_layer_kind (merged layer kind other) including the 2 triage-NEW tests, plus test_project_tags/test_vcs_project_completion insertion-order failures, test_agent_header_panel scroll assertion, usage transport deadline flake, and symvision stale --epic-symbol entries owned by sase-19x.4/sase-19f/sase-18i — none touched by this phase

[2026-09-26T13:20:07Z · sase-19x.8--1] Block rail done: block_rail_text renderer + BlockRail widget docked in Main deck panel. Verified: 12/12 new test_deck_block_rail.py pass, 281/281 decks suite pass, sase bead epic-symbols clean (no entries). just check red is pre-existing on clean base (stashed run reproduces axe-config/project-tags/vcs failures); recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-19x.6](sase-19x.6.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-19x.9](sase-19x.9.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.8.md) | [sase-19x.8](sase-19x.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f7df95c`](https://github.com/sase-org/sase/commit/f7df95c94c0fc5a2498968ce46fec815444cd020) | feat(ace-tui): one-row block rail under Main deck panel (sase-19x.8) | [sase-19x.8](sase-19x.8.md) | 2026-09-26 09:21:28 EDT |

# Bead: sase-19x.4 — Blocks for the legacy followup\_agents Reply path

[Bead Pages](../README.md) / [sase-19x](README.md) / sase-19x.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s4.md) · **Assignee:** `sase-19x.4` · **Size:** small
**Created:** 2026-09-25 20:37:43 EDT · **Closed:** 2026-09-26 07:31:53 EDT
**Plan:** [202609/agent\_data\_card\_blocks.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_data_card_blocks.md)

## Description

legacy-followup-blocks: give the still-reachable non-session followup_agents Reply path the same per-phase blocks in both modes. This splits its single-Text hint twin per phase and adds the missing gate branch.

## Notes

[2026-09-26T10:53:33Z · sase-19x.4] PROPOSED FOLLOW-UP: visual PNG goldens may need refresh for legacy followup_agents Reply heading (AGENT REPLY now carries a phase count and per-phase blocks) — 19x.9 golden inspection should cover it

[2026-09-26T10:53:43Z · sase-19x.4] PROPOSED FOLLOW-UP: test_files_ctrl_j_scrolls_page_anchor_to_top failed once in a full parallel widgets run but passes alone — possible timing flake under load

[2026-09-26T11:31:34Z · sase-19x.4--1] PROPOSED FOLLOW-UP: just check full-lane flakes test_files_ctrl_j_scrolls_page_anchor_to_top and test_snapshot_includes_live_config_token_refresh_threads both pass alone; unrelated to prompt_panel phase changes

[2026-09-26T11:31:53Z · sase-19x.4--1] Legacy followup Reply per-phase blocks verified: 7/7 new tests pass; deck ctrl-j and global-state flakes pass alone and are unrelated (prompt_panel vs deck widget); no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-19x.3](sase-19x.3.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-19x.9](sase-19x.9.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.4.md) | [sase-19x.4](sase-19x.4.md) | 0 |

# Bead: sase-19x.11.1 — Keep the scrollbar in sync across card-block mode changes

[Bead Pages](../README.md) / [sase-19x.11](sase-19x.11.md) / sase-19x.11.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19x.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.land.md) · **Assignee:** `sase-19x.11.1` · **Size:** medium
**Created:** 2026-09-26 14:47:58 EDT
**Plan:** [202609/card\_block\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/card_block_landing_gaps.md)

## Description

scrollbar-transition: remove the block-spread to block-paged scrollbar desynchronization and its snapshot workaround; add a focused regression.

## Notes

[2026-09-26T19:12:39Z · sase-19x.11.1] PROPOSED FOLLOW-UP: block visual PNG fixtures still build Agents with retired agent_session fields and fail in runner_capacity_snapshot on current master (sase-1ab.5 turn rename fallout); micro golden refresh blocked, goldens untouched — repair fixtures then rerun fix-tui-screenshots for test_ace_png_snapshots_agents_deck_blocks.py

[2026-09-26T19:12:51Z · sase-19x.11.1] PROPOSED FOLLOW-UP: new-subject tall-to-short document swap leaves ScrollBar.position stale the same way (pos 6 vs scroll 0 probed in /tmp/repro_subject.py); same one-line immediate+sync fix applies in MainDeckView.show_document is_new_subject branch — left out of scope as no mode change

## Dependencies

- **Blocks:** [sase-19x.11.2](sase-19x.11.2.md) ◐ · ⧖ 2026-09-26
- **Blocks:** [sase-19x.11.3](sase-19x.11.3.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.11.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.11.1.md) | [sase-19x.11.1](sase-19x.11.1.md) | 0 |

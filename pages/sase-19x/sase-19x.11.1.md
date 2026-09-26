# Bead: sase-19x.11.1 — Keep the scrollbar in sync across card-block mode changes

[Bead Pages](../README.md) / [sase-19x.11](sase-19x.11.md) / sase-19x.11.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19x.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.land.md) · **Assignee:** `sase-19x.11.1` · **Size:** medium
**Created:** 2026-09-26 14:47:58 EDT · **Closed:** 2026-09-26 16:16:04 EDT
**Plan:** [202609/card\_block\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/card_block_landing_gaps.md)

## Description

scrollbar-transition: remove the block-spread to block-paged scrollbar desynchronization and its snapshot workaround; add a focused regression.

## Notes

[2026-09-26T19:12:39Z · sase-19x.11.1] PROPOSED FOLLOW-UP: block visual PNG fixtures still build Agents with retired agent_session fields and fail in runner_capacity_snapshot on current master (sase-1ab.5 turn rename fallout); micro golden refresh blocked, goldens untouched — repair fixtures then rerun fix-tui-screenshots for test_ace_png_snapshots_agents_deck_blocks.py

[2026-09-26T19:12:51Z · sase-19x.11.1] PROPOSED FOLLOW-UP: new-subject tall-to-short document swap leaves ScrollBar.position stale the same way (pos 6 vs scroll 0 probed in /tmp/repro_subject.py); same one-line immediate+sync fix applies in MainDeckView.show_document is_new_subject branch — left out of scope as no mode change

[2026-09-26T20:15:40Z · sase-19x.11.1--2] PROPOSED FOLLOW-UP: just check red on clean base too — stale symvision --epic-symbol sase-19i.7.3.3.2(describe_node_finder_row_from_facts) (bead closed) in Justfile _lint-symvision; needs owner cleanup

[2026-09-26T20:15:50Z · sase-19x.11.1--2] PROPOSED FOLLOW-UP: full-suite test-scoped failures reproduce identically on clean base (proc/parser/completion-snapshot/identity/node-finder/deck-empty-kinds, ~90 NEW incl. sase-1ab.5 turn-rename fallout); unrelated to scrollbar-sync diff, needs land-agent triage

[2026-09-26T20:16:04Z · sase-19x.11.1--2] Scrollbar desync fixed via immediate scroll_to + deferred _sync_scrollbar_position in main_view_blocks/panel_transitions; snapshot workaround removed; new regression test_block_spread_to_paged_keeps_scrollbar_in_sync passes (14/14 pilot file). ruff clean, test-waits lint clean, no epic-symbols. Remaining just-check reds (stale 19i symvision symbol, ~90 base-tree test failures) reproduce identically on clean base, recorded as follow-ups.

## Dependencies

- **Blocks:** [sase-19x.11.2](sase-19x.11.2.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-19x.11.3](sase-19x.11.3.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.11.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.11.1.md) | [sase-19x.11.1](sase-19x.11.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bff09e3`](https://github.com/sase-org/sase/commit/bff09e3cf1e5c052d4c614c381db71cb79b091ee) | fix(ace-tui): sync block-paged scrollbar on block-spread transition | [sase-19x.11.1](sase-19x.11.1.md) | 2026-09-26 16:17:57 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19x.11.1--2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.11.1.md

<!-- sase:referenced-by:end -->

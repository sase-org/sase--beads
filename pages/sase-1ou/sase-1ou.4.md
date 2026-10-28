# Bead: sase-1ou.4 — Fix the Files ctrl+j page-anchor scroll race (sase-1a7)

[Bead Pages](../README.md) / [sase-1ou](README.md) / sase-1ou.4

**Status:** ○ open · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1oh.land--1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.land.md) · **Assignee:** `sase-1ou.4` · **Size:** large
**Created:** 2026-10-27 09:20:59 EDT
**Plan:** [202610/backlog\_epic\_2\_top\_five\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/backlog_epic_2_top_five_task_beads.md)

## Previously Closed

> ↺ Closed 2026-10-27T16:10:55Z · done
>
> (none)
>
> Reopened 2026-10-28T20:58:42Z by `sase bead open`

## Description

deck-anchor: reproduce the intermittent wait_for_anchor_scroll timeout in test_files_ctrl_j_scrolls_page_anchor_to_top (it fails about 1 in 4 even in isolation), fix the Files spread scroll/anchor race in production code, prove it with isolated and loaded stress loops, and close sase-1a7.

## Notes

[2026-10-27T15:37:17Z · sase-1ou.4] Phase sase-1ou.4 evidence (before monitor handoff):

Cause: Files spread Ctrl-J race had two backlog-era gaps. (1) Hidden paged AgentFilePanel shares the same VerticalScroll as FilesSpreadView; its anchor capture/restore had no visibility guard, so a delayed static-read restore reset spread scroll_y 6->0 (reproduced deterministically). (2) Spread navigation used an 8-attempt call_after_refresh chain with no pending state; late anchors/reserve after the burst abandoned the request. Rapid Ctrl-J also recomputed from stale scroll_y instead of pending, and the scroll watcher re-derived during flight.

Fix (presentation-only, this repo):
- src/sase/ace/tui/widgets/file_panel/_content.py: hidden paged view never captures or applies scroll anchors (_is_hidden_for_scroll guard in _capture/_apply/_note_slot_change).
- src/sase/ace/tui/widgets/decks/panel_spread.py: pending Files navigation (_files_pending_scroll_index/generation/retry/confirmed), immediate scroll_to, two-consecutive confirm, layout resume via _reschedule_files_scroll_after_layout, superseding chains from pending, unmount clears.
- src/sase/ace/tui/widgets/decks/files_spread.py: _publish_section_layout resumes pending navigation.
- src/sase/ace/tui/widgets/decks/panel_files.py: transitions and new-subject probe bump generation and clear pending.
- src/sase/ace/tui/widgets/decks/panel.py: leaving spread clears pending.
- src/sase/ace/tui/widgets/decks/panel_interaction.py: scroll watcher holds pending page instead of re-deriving.
- tests/ace/tui/widgets/decks/test_files_anchor_ownership.py: 4 real-widget regression tests (hidden restore, visible restore+return offset, supersede+manual hold, late-layout resume).

Before (base 98668bf4313401248966b09d896b417eadd82259, Python 3.14.7, textual 8.0.1, 64 cores, load ~18-34, 6x yes/busy-loop load, core pin 800caef4c70039ccf299a0ecca379142f80234c2):
- 50 isolated test_files_ctrl_j_scrolls_page_anchor_to_top: 50 passed, 0 failed.
- 5x tests/ace/tui/widgets/decks/ -n6: 5 passed (708 each), 0 failed.
- Natural loop green, so induced interleaving required: hidden paged restore moved scroll 6->0 (probe). New regression on stashed base: 3 failed, 1 passed (visible-restore coverage passes both).

After (same env/load):
- 50 isolated: 50 passed, 0 failed.
- 5x decks/ -n6: 5 passed (712 each with new tests), 0 failed.
- 10x new regression file: 10 passed, 0 failed.
- Focused: test_deck_spread_pilot + new + spread_landing + file_panel anchor/async (67 passed).
- Original pilot unchanged as e2e check.
- Baseline: no entry for exact node (rechecked); no suppression added. selection_health --fail-on-new-flake exit 0 (other owners exceedances separate). epic-symbols sase-1ou.4: none.
- just fmt pass; check_test_wait_helpers pass after pause-loop fix.
- sase tool run check 0832dea1c87b939b0133374d264d28ba: all lint gates pass (fmt, keep-sorted, ruff, mypy, feature-flags, pyscripts, test-waits, changelog, terminology, symvision, docs, SASE validation, committed plans); test lane still running at handoff (handed to monitor). No visual goldens changed (no rendered-output change); targeted PNG run deferred to monitor if needed.

Lander: close sase-1a7 on this evidence; no memory edits, no new beads, no ancestor closes. Baseline disposition: node remains absent, add nothing.

[2026-10-27T16:10:55Z · sase-1ou.4--1] Verified Files ctrl+j page-anchor race fix. Cause: hidden paged AgentFilePanel shared VerticalScroll anchor restore reset spread scroll_y 6->0 with no visibility guard; spread navigation 8-attempt call_after_refresh chain with no pending state abandoned late anchors, recomputed from stale scroll_y, watcher re-derived during flight. Fix: hidden paged view never captures/applies anchors (_is_hidden_for_scroll); pending Files navigation with immediate scroll_to, two-consecutive confirm, layout resume, superseding chains, unmount clears; _publish_section_layout resumes pending; transitions/new-subject bump generation; leaving spread clears pending; scroll watcher holds pending page. Regression: tests/ace/tui/widgets/decks/test_files_anchor_ownership.py 4 real-widget tests (hidden restore, visible restore+return offset, supersede+manual hold, late-layout resume) — 10x runs green, 5x decks -n6 green (712 each), 50x isolated target test green, 67 focused tests green. Stress: 6x yes/busy-loop load, core pin, same env as before. Check: sase tool run check 0832dea1c87b939b0133374d264d28ba verdict no_new_failures (3 KNOWN pre-existing: 2x snapshot drift witness 12ddc4cc6cb7331ddf8d6fddd35d571d, 1x import budget witness 01564beb93f5085605d33a22bce43f1f; touched=false, possible_owners empty). selection_health --fail-on-new-flake exit 0. epic-symbols sase-1ou.4 none. Baseline tests/reproducible_flake_baseline.txt has no entry for exact node, left absent. Leaving sase-1a7 and ancestors for lander.

## Dependencies

- **Depends on:** [sase-1ou.1](sase-1ou.1.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.4.md) | [sase-1ou.4](sase-1ou.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`691ef46`](https://github.com/sase-org/sase/commit/691ef461533d08759fa6d2fce30eee7bac48bddb) | fix(ace-tui): resolve Files ctrl+j page-anchor scroll race | [sase-1ou.4](sase-1ou.4.md) | 2026-10-27 12:12:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ou.4--1][1] | final verification before close | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.4.md

<!-- sase:referenced-by:end -->

# Bead: sase-1i5.7 — Deterministic deck anchor-scroll settling (sase-1br)

[Bead Pages](../README.md) / [sase-1i5](README.md) / sase-1i5.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y8.md) · **Assignee:** `sase-1i5.7` · **Size:** medium
**Created:** 2026-10-08 09:47:21 EDT
**Plan:** [202610/close\_top\_ten\_impact\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/close_top_ten_impact_task_beads.md)

## Description

deck-scroll-settle: root-cause and fix the deck anchor-scroll settle race behind the block-spread pilot timeout, share one settle wait across deck pilots, prove stability by repetition, and close sase-1br.

## Notes

[2026-10-08T14:34:31Z · sase-1i5.7] Root cause (sase-1br): deck anchor-scroll landing converges over multiple layout frames (async anchor publication + trailing reserve convergence), but pilot tests snapshotted spread_landing_target()/block_header_row() once and waited 5s for scroll equality with the stale value; whenever capture lands pre-convergence the wait can never succeed. Probe evidence (/tmp/deck_settle_probe.py, /tmp/deck_probe2.py): landing needs attempts 0-2 to converge even in passing runs; deferred (non-immediate) scroll_to application lags >=1 frame behind the call (attempt-0 scroll invisible at attempt-1 poll). Fix is test-side per phase branch 2: new shared wait_for_anchor_scroll helper (tests/ace/tui/widgets/decks/_deck_settle.py) re-reads the live target every poll and requires scroll==same-target on 2 consecutive settles; all 7 snapshot waits in test_deck_block_spread_pilot.py + 2 scroll-settle waits in test_deck_spread_pilot.py converted. NO product change: making landing scrolls immediate was tried and reverted - synchronous scroll fires _on_main_scroll_y watchers re-entrantly, re-deriving the cursor from transitional layout and clobbering explicit steps (broke 2 cursor tests deterministically); deferred ordering is load-bearing. No timeout raised (still 5s).

[2026-10-08T14:34:49Z · sase-1i5.7] PROPOSED FOLLOW-UP: make_agent/make_artifact_agent deck tests fail deterministically with RuntimeError sase_core_rs content-layout wire is stale (expected schema >= 7, got 5) from src/sase/core/content_layout_wire.py:227 - blocks test_files_ctrl_j_scrolls_page_anchor_to_top (sase-1a7) and other tmp_path agent-fixture tests in this workspace; reproduces identically on clean tree with tests/ stashed, so environmental/pre-existing, not the scroll-settle flake.

## Dependencies

- **Blocks:** [sase-1i5.8](sase-1i5.8.md) ◐ · ⧖ 2026-10-08
- **Blocks:** [sase-1i5.9](sase-1i5.9.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1i5.7/README.md) | [sase-1i5.7](sase-1i5.7.md) | 0 |

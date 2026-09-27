# Bead: sase-1b1.8.4.1 — Make prebuilt deferred bodies match the synchronous render and re-apply the landing edits

[Bead Pages](../README.md) / [sase-1b1.8.4](sase-1b1.8.4.md) / sase-1b1.8.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1b1.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.8.land.md) · **Assignee:** `sase-1b1.8.4.1` · **Size:** medium
**Created:** 2026-09-27 17:36:38 EDT · **Closed:** 2026-09-27 18:32:04 EDT
**Plan:** [202609/deck\_views\_prebuilt\_paint\_fidelity.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views_prebuilt_paint_fidelity.md)

## Description

fidelity: render prebuilt Main bodies through the same console settings and widget post_render base style that Textual's RichVisual uses, with a strip-equality regression test. Re-apply the land agent's FINAL-flag test and Deck Views docs edits.

## Notes

[2026-09-27T22:31:03Z · sase-1b1.8.4.1] Fidelity fix landed: prebuilt Main bodies now render through capture_prebuilt_context (UI thread: app.console_options snapshot + view.post_render wrap under last compositor base style + style token) and build_prebuilt_offthread (worker: mirror Console markup=True emoji=False safe_box=False force_terminal=True soft_wrap=False + options.update(highlight=False,width,height=None).update_width). Root cause proved by probes: empty base style drops all unstyled segments via Textual _Styled link_style filter, and missing panel bg #121212 caused the grey header drift. Store key is now (digest,width,style_token); token miss falls back to sync render.

[2026-09-27T22:31:28Z · sase-1b1.8.4.1] Verify: new tests/ace/tui/widgets/decks/test_deck_view_prebuilt_fidelity.py (strip text+style equality for page_cards/spread/page_blocks + style-token serve gate) 4 passed; decks/ dir 442 passed; decks/final + 5 section-nav files + member_jump 107 passed; persistence 23 passed; main/files pilots + keys + card_block_model + spread_pure 104 passed. Lint: fmt/ruff/mypy/feature-flags/pyscripts/test-waits/changelog/terminology all pass; symvision triage 71 KNOWN 0 NEW (also fixed pre-existing _segment_section_identity misuse by promoting segment_section_identity/textual_style_token to public, and deleted dead _applied_generation getter). just check test lane could not finish in-turn: scoped selection escalates to FULL_SUITE (4466 files) and host load avg was 24.

[2026-09-27T22:31:43Z · sase-1b1.8.4.1] PROPOSED FOLLOW-UP: decks/final/test_final_live.py::test_slow_retrying_finalizer_projects_active_tail_end_to_end fails with sase_core_rs missing project_finalizer_node_view; reproduces identically on clean base tree (verified via stash), needs Rust extension rebuild/pin. PROPOSED FOLLOW-UP: bench_tui_deck_view standard-5k p95 budget (300ms) missed on one transition per run on both trees (mine: page_blocks_to_spread p95 928ms max 1023ms; base: spread_to_page_blocks p95 945ms max 1231ms) under host load avg 24; p50s hold 28-45ms vs 150ms budget. Looks like shared-host noise, consider warmup exclusion or budget revisit.

[2026-09-27T22:32:04Z · sase-1b1.8.4.1] Fidelity fix verified: new prebuilt strip-equality test (4 passed); decks/ 442 passed; section-nav + final 107 passed (1 pre-existing rust-binding failure, base-reproduced); persistence 23 passed; pilots/keys 104 passed; lint gates pass with symvision 0 NEW; land-agent FINAL-flag test renames and Deck Views docs edits re-applied; no ace_final_deck references remain; bench p50s hold (p95 outlier pre-existing on base under host load)

## Dependencies

- **Blocks:** [sase-1b1.8.4.2](sase-1b1.8.4.2.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.8.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b1.8.4.1/README.md) | [sase-1b1.8.4.1](sase-1b1.8.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b9cfa73`](https://github.com/sase-org/sase/commit/b9cfa7386327e484ee600a8ba2a578f0a042292b) | feat(decks): match prebuilt deferred Main bodies to the synchronous render | [sase-1b1.8.4.1](sase-1b1.8.4.1.md) | 2026-09-27 18:40:27 EDT |

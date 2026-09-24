# Bead: sase-17d.10.1.3 — Regenerate and inspect every affected PNG golden

[Bead Pages](../README.md) / [sase-17d.10.1](sase-17d.10.1.md) / sase-17d.10.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17d.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.10.md) · **Assignee:** `sase-17d.10.1.3` · **Size:** medium
**Created:** 2026-09-24 10:13:47 EDT
**Plan:** [202609/deck\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_cutover.md)

## Description

cutover-goldens: run the full just fix-tui-screenshots through /sase_monitor, inspect every creation, removal and update group, fix any rendering regression it reveals, capture live deck screenshots, and run the final j/k perf bench.

## Notes

[2026-09-24T20:00:59Z · sase-17d.10.1.3--1] cutover-goldens status: full just fix-tui-screenshots update was partial (138 updated, 574 unchanged, 28 nodes failed deterministic, stale goldens left). Fixed 3 tests: 2 deck card-nav source bugs + 1 mock-sig. Scoped regen applied for the 2 deck goldens. --check NOT clean (24 legacy-migration failures remain); bead left open.

[2026-09-24T20:01:18Z · sase-17d.10.1.3--1] PROPOSED FOLLOW-UP: migrate 24 legacy visual tests to deck API and regen stale goldens (slow_tools fold, tribe_clan_summaries, tribe four_level, tribe_prompts, waiting unknown_zoom_modal (zoom modal deleted), swarm_clan_panel, external_repo diff_file, family_panel fold_levels, linked_repo diff_file, linked_repo commit_messages, metadata_search typing_committed, gate_shell_output, monitor_state_detail x7, family shells_monitor_metadata, family conversation_monitor_phase, agents_collapsed_panel, top_bar usage_attention_narrow, top_bar usage_badges_crowded, llm_calls detail full). All fail deterministic on deleted section/nav APIs (active_section_identity None, #agent-prompt-scroll/#agent-file-scroll/#agent-search-command NoMatches, AgentInfoPanel._view_mode).

[2026-09-24T20:01:29Z · sase-17d.10.1.3--1] PROPOSED FOLLOW-UP: repair j/k bench harness for decks (7/10 bench tests fail: clan/tribe fold levels, link_rail, axe samples assert, fleet faults over budget) and record SINGLE vs LEFT_RIGHT p50/p95 vs sase-17d.3 baselines; current numbers noisy (rail-absent next p50 15.36/p95 34.99 with 370ms max outlier vs baseline p95 19.28).

[2026-09-24T20:01:48Z · sase-17d.10.1.3--1] PROPOSED FOLLOW-UP: add missing coverage goldens (spread Files, paged-after-threshold per sase-17d.8 notes, LEFT_RIGHT committed-search overlay per sase-17d.6 notes); spread Main already covered by agents_decks_single_main_reply_120x40.

[2026-09-24T20:01:58Z · sase-17d.10.1.3--1] PROPOSED FOLLOW-UP: capture live sase screenshot PNGs (single Main, Main|Files split, Context|Reply, collapsed node panel, zoomed panel) and inspect; skipped here (headless). Also check deck detail border-title clipping (border shows clipped label near tab strip) seen in regenerated deck goldens.

[2026-09-24T20:02:09Z · sase-17d.10.1.3--1] Source fix detail: spread card nav lost explicit selection on same-subject re-push (_show_document_spread re-derived from stale scroll while scroll_to pending; PAGED->SPREAD transitions and _refresh_main_mode_for_shown dropped preferred). Fixed in main_view.py (pending-guard, 2 branches) and panel.py (one-shot across transitions + mode-refresh honors preferred). Deck unit tests 155 passed; ruff clean; scoped --check 3/3 green.

## Dependencies

- **Depends on:** [sase-17d.10.1.2](sase-17d.10.1.2.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.10.1.3.md) | [sase-17d.10.1.3](sase-17d.10.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`37c8bb2`](https://github.com/sase-org/sase/commit/37c8bb26438cf1212fcfe24b44f7817b5c5753dc) | fix(ace-decks): preserve pending spread card across re-push and split | [sase-17d.10.1.3](sase-17d.10.1.3.md) | 2026-09-24 16:04:11 EDT |

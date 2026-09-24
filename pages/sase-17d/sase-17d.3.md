# Bead: sase-17d.3 — Deck panel core behind the agent\_decks beta flag

[Bead Pages](../README.md) / [sase-17d](README.md) / sase-17d.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qd.md) · **Assignee:** `sase-17d.3` · **Size:** large
**Created:** 2026-09-23 19:16:49 EDT · **Closed:** 2026-09-23 21:28:39 EDT
**Plan:** [202609/agents\_tab\_decks\_and\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_decks_and_cards.md)

## Description

deck-panel-core: create the agent_decks beta flag and the widgets/decks package: DeckArea with two pre-composed DeckPanels, a hidden Main source feeding MainDeckViews, per-panel Files and Tools views, tab-strip titles, empty-state cards, lazy loading and no-I/O availability probes. Paged rendering only.

## Notes

[2026-09-24T00:55:06Z · sase-17d.3] agent_decks flag bead: sase-17k (deck-cutover closes it)

[2026-09-24T01:26:18Z · sase-17d.3] bench j/k after (flag off): next rail-absent p50 16.38/p95 23.93, prev p50 15.39/p95 22.45; rail-painting next p50 16.73/p95 22.45, prev p50 13.76/p95 20.10 (n=44). No pre-change baseline was captured. Fleet-fault scenarios (hung_host/reconnect_churn/event_burst) exceed the 16ms p95 budget on this shared host (event_burst next p95 19.44/prev 20.88, max 307ms outlier); likely host noise, needs a quiet-host rerun.

[2026-09-24T01:26:58Z · sase-17d.3] bench j/k after (flag ON, SASE_FEATURE_FLAGS={"agent_decks": true}): next rail-absent p50 14.44/p95 19.28, prev p50 14.84/p95 21.85; rail-painting next p50 15.53/p95 21.92, prev p50 13.91/p95 18.30 (n=44). No flag-on regression vs flag-off on the same host (on is nominally faster; noise dominates). Section-5 target j/k p95 <16ms SINGLE is not met by either state on this shared host.

[2026-09-24T01:27:26Z · sase-17d.3] HANDOFF for deck-navigation-keys/deck-splits-focus/deck-action-retarget/node-panel-collapse-zoom/deck-cutover: (1) Temporary D12 guards: p blocked in actions/agents/_agent_view_picker.py (_agent_view_picker_block_reason) + palette app.choose_agent_view forced False in commands/_availability_agents.py (new ctx.agent_decks_active plumbed via commands/context.py + types.py); Z blocked in _app_action_availability.py (check_app_action) + action_zoom_panel no-op in actions/agents/_panel_detail.py + palette app.zoom_panel False; view: chip forced "" in actions/agents/_display_detail_info.py; metadata search returns False in deck mode in actions/agents/_metadata_search.py (deck-action-retarget replaces with per-panel overlay). (2) Hidden compat host: #agent-deck-source-host keeps #agent-prompt-scroll/#agent-search-scroll/#agent-search-panel/#agent-search-command resolvable but display:none; deck-cutover deletes it. Legacy #agent-file-scroll/#agent-llm-calls-scroll NOT composed in deck mode; accessors rerouted. (3) AgentDetail deck API: show_deck(panel_index, deck), set_deck_preferred_card(panel_index, card_id), deck_area, decks_enabled. (4) Empty-state hint is still None (keys land in deck-navigation-keys). (5) deck_title unfocused styling parameterized; TCSS :not() unfocused border rules were dropped because Textual rejects :not — splits phase owns unfocused chrome.

[2026-09-24T01:28:01Z · sase-17d.3] PROPOSED FOLLOW-UP: just _lint-symvision fails identically on the pristine tree (repo-wide private-import errors in untouched files, e.g. llm_provider/usage); needs a dependency/pin investigation, not a deck fix. PROPOSED FOLLOW-UP: rerun the fleet-fault j/k bench on a quiet host to confirm the p95>16ms misses are noise. PROPOSED FOLLOW-UP: live PNGs captured for flag-on Main-content and flag-off legacy only; no-selection and tribe-summary states are pilot-test covered, first flag-on goldens land in deck-navigation-keys per plan.

[2026-09-24T01:28:39Z · sase-17d.3] deck-panel-core implemented: agent_decks beta flag (bead sase-17k), widgets/decks package (model/main_document/titles/empty_state/availability/flag/main_view/panel/area), SectionViewMixin extraction, hidden Main source + DeckArea compose, lazy Files/Tools loading, D12 p/Z/chip/search guards, CSS. Verified: 43 new deck tests pass; file/llm/zoom/agent_detail lane 312 pass + panel-mode mock fixed; ruff/mypy/feature-flags/toobig clean; live workspace PNGs confirm flag-on deck frame (MAIN title, main/files/tools subtitle) and unchanged flag-off legacy. No PNG goldens changed (flag off by default). Known pre-existing issues noted on bead (symvision red on clean tree, fleet bench p95 on shared host).

## Dependencies

- **Depends on:** [sase-17d.1](sase-17d.1.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-17d.2](sase-17d.2.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17d.4](sase-17d.4.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.3.md) | [sase-17d.3](sase-17d.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`00ee519`](https://github.com/sase-org/sase/commit/00ee51996d109f2715701b4140f7b528520764de) | feat(agents-tui): deck panel core behind the agent\_decks beta flag | [sase-17d.3](sase-17d.3.md) | 2026-09-23 21:30:43 EDT |

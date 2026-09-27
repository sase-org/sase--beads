# Bead: sase-1b2.18 — Live tails, following, and the 1 Hz tick for the selected agent

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.18

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.18` · **Size:** medium
**Created:** 2026-09-27 05:49:52 EDT · **Closed:** 2026-09-27 12:25:07 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

final-live: add the ace.agent_decks.final_tail_delay_seconds gate and a sanitized in-card live tail of at most 12 lines. The tail follows the newest run and attempt with the arrival marker, pauses on scroll-up, and runs a pump-free 1 Hz elapsed/tail refresh only while FINAL shows the selected agent's active finalization.

## Notes

[2026-09-27T15:56:36Z · sase-1b2.18] PROPOSED FOLLOW-UP: tests/ace/tui/widgets/decks/test_card_document_view.py::test_card_document_decks_is_main_only and test_deck_picker.py::test_picker_catalog_covers_every_deck fail identically on the clean base tree (verified via stash); CARD_DOCUMENT_DECKS now includes FINAL and picker keys/cycle disagree — likely owned by card-document-view (sase-1b2.11) or final-deck-shell follow-up, not final-live

[2026-09-27T16:25:07Z · sase-1b2.18] final-live done and verified: ace.agent_decks.final_tail_delay_seconds gate (default 5.0; 0=immediate) in agent_decks_settings.py + default_config.yml + sase.schema.json with parser/parity tests; new decks/final/live.py owns gate/sanitize/newest-run+latest-attempt follow/follow-pause/1Hz tick predicates + FinalLiveTicker; in-card live tail (<=12 lines, render_axe_output ansi, elapsed header) threaded through instance_card/document/loader; FinalDeckView owns the pump-free 1Hz tick (nav+typing gates, cancel on hide/subject-change/settle/teardown) with scroll-up pause/bottom resume; fixed latent ...models import-depth bug in view update_display. Tests: 27 new (incl. sealed-plan+open-journal e2e over the real Rust projection showing active tail + closed gate), 129 green across FINAL/config/adapter suites; ruff+format+mypy clean; symvision set-diff vs base is empty; toobig clean (instance_card 699). Two deck tests fail identically on base (recorded as PROPOSED FOLLOW-UP). Full just check could not run: shared sase-core rebuild lock timed out setup twice (environmental). No epic-symbols remain.

## Dependencies

- **Depends on:** [sase-1b2.17](sase-1b2.17.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.19](sase-1b2.19.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.18](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.18/README.md) | [sase-1b2.18](sase-1b2.18.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ed0b66f`](https://github.com/sase-org/sase/commit/ed0b66f7b8e02100edbb351d7912f8425ee34cf8) | feat(final-deck): add gated 1 Hz live tail for actively-finalizing nodes | [sase-1b2.18](sase-1b2.18.md) | 2026-09-27 12:27:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |
| read-by | [agent:sase-1b2.18][2] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.18/README.md

<!-- sase:referenced-by:end -->

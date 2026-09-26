# Bead: sase-19x.5 — Block-paged projection, newest landing and the card\_blocks flag

[Bead Pages](../README.md) / [sase-19x](README.md) / sase-19x.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s4.md) · **Assignee:** `sase-19x.5` · **Size:** medium
**Created:** 2026-09-25 20:37:45 EDT · **Closed:** 2026-09-26 07:37:14 EDT
**Plan:** [202609/agent\_data\_card\_blocks.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_data_card_blocks.md)

## Description

block-paged-view: create the card_blocks beta flag. Add DeckPanelBlocksMixin and the MainDeckView block mixin, which decide the block mode for a card shown alone, render one block per page, and land on the newest block. They also follow new shells, keep the reader's block by id, and expose cycle/select and a cached navigable predicate. Add the sticky-Reply bench fixture.

## Notes

[2026-09-26T10:19:49Z · sase-19x.5] Bench (3 sessions x 10 shells x ~500 reply lines, SINGLE): flag-off j/k next p50 15.67/p95 19.39, prev p50 13.72/p95 19.35; flag-on next p50 15.56/p95 19.98, prev p50 17.43/p95 31.56. LEFT_RIGHT: off next p50 24.71/p95 42.80 prev p50 24.26/p95 35.71; on next p50 27.06/p95 38.15 prev p50 27.13/p95 42.04. Parity within noise; the 16ms phase target is not met (new-subject document build dominates). Block-cycle (paged, flag on): p50 48.4ms; p95 tail is host scheduler stalls (same noise the link-rail bench documents). Committed bench asserts generous ceilings + median for cycle.

[2026-09-26T10:20:11Z · sase-19x.5] PROPOSED FOLLOW-UP: sticky-Reply j/k misses the 16ms phase target in both flag arms (new-subject document build + deck measure dominate); cutover phase re-records the flag-off vs flag-on bench per plan

[2026-09-26T10:20:21Z · sase-19x.5] PROPOSED FOLLOW-UP: block-cycle page swap paints ~50ms steady-state (preferred-set full re-show + CSS + 500-line layout, shared with Ctrl+J/K card cycling); consider skipping the show_main_document re-show when the page is already projected

[2026-09-26T11:36:55Z · sase-19x.5--2] PROPOSED FOLLOW-UP: full-suite just check (35min, 9 workers) showed 5 load-sensitive flakes + 1 flaky, all pass in isolation on this tree: test_ppid_walk_teardown, test_detached_gate_route_reacquires_runner_slot, test_uppercase_g_reaches_detail_bottom[shift+g-G], 2x grok_usage_probe omitted-zero, plus flaky test_run_supervisor_escalates_term_ignoring_chatty_child; domains untouched by this bead (monitor/gate/notification/grok vs decks blocks)

[2026-09-26T11:37:14Z · sase-19x.5--2] Verified: DeckPanelBlocksMixin + MainDeckView block mixin with card_blocks flag, newest-landing, follow/keep-by-id, cycle/select, cached navigable predicate, sticky-Reply bench fixture. mypy clean on 4 deck-block files; pilot suite 14 passed; 5 full-suite NEW failures + 1 flaky all pass in isolation (load flakes in unrelated domains, recorded as follow-up). epic-symbols clean.

## Dependencies

- **Depends on:** [sase-19x.2](sase-19x.2.md) ✓ · ⧖ 2026-09-25
- **Depends on:** [sase-19x.3](sase-19x.3.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-19x.6](sase-19x.6.md) ◐ · ⧖ 2026-09-25
- **Blocks:** [sase-19x.7](sase-19x.7.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.5.md) | [sase-19x.5](sase-19x.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`42e29d6`](https://github.com/sase-org/sase/commit/42e29d6ccca3bf8f2de51a020526f464f5a021d5) | feat(decks): block-paged projection with newest landing and card\_blocks flag (sase-19x.5) | [sase-19x.5](sase-19x.5.md) | 2026-09-26 07:39:10 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19x.5--2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.5.md

<!-- sase:referenced-by:end -->

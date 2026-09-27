# Bead: sase-1b1 — Deck views: see and choose how a deck panel pages its cards and blocks

[Bead Pages](../README.md) / sase-1b1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sx.md) · **Assignee:** `sase-1b1.land`
**Created:** 2026-09-27 05:45:14 EDT
**Plan:** [202609/deck\_views.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/deck_views.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/deck_views.md

<!-- sase:links:end -->

## Description

Every Main and Files deck panel names its effective view (spread, page cards, or page blocks) and whether it is automatic or fixed, in a stable, text-first badge in the top border. `P` cycles the focused panel through the valid views without losing the reader's place. Palette commands pick a view directly or return to automatic. Choices persist per panel and per deck across agents, splits, zoom, and restarts.

## Notes

[2026-09-27T10:06:58Z · 0t2] CROSS-EPIC COORDINATION with sase-1b2 (the FINAL deck, plan:202609/agents_tab_final_deck.md). The two epics run concurrently and edit the same deck-panel code, and neither plan mentions the other.
Overlap map:
- 1b1.1 <-> 1b2.10 (+1b2.9): DeckPanelState, with_* helpers, deck-state persistence.
- 1b1.2/1b1.3 <-> 1b2.11: deciders, block host, transitions (CardDocumentView extraction).
- 1b1.4 <-> 1b2.9/1b2.11/1b2.14: titles, subtitle, panel chrome, rail.
- 1b1.5 <-> 1b2.9/1b2.14: palette, footer, help, deck-set tests.
- 1b1.6 <-> 1b2.19: goldens and bench.
- 1b1.7 <-> 1b2.20: docs.
Likely order: 1b1's chain finishes before 1b2.14+, which wait on sase-core work. The live races are therefore 1b1.1 vs 1b2.9/1b2.10 and 1b1.2-1b1.4 vs 1b2.11. Each affected phase bead carries specific instructions.

SHARED RULES (the same list is on both sase-1b1 and sase-1b2; these are defaults the user may override):
R1 Scope: deck views stay Main+Files only. FINAL, like Tools, is permanently AUTO: no title badge; `P` and the "Deck view: ..." palette commands are unavailable; no `final` key in persisted `views`. Its spread/paged and block modes stay automatic. The epic that lands second records `PROPOSED FOLLOW-UP: extend deck views (policy, badge, P) to the FINAL deck`.
R2 Explicit dispatch: view code tests `deck is DeckId.MAIN` / `deck in (MAIN, FILES)`, never "not Tools" or an else fall-through (1b2.9's rule). `DeckViewPolicies.for_deck()` returns AUTO, and `with_deck()` rejects every deck other than Main/Files.
R3 State: `DeckPanelState` carries both `views` (1b1.1) and the per-deck preferred-card mapping (1b2.10). `with_panel_deck`, `with_preferred_card`, `with_panel_view`, `layout.new_panel_for_deck`/`choose_new_panel` and `area_state_from_snapshot` build panels with `dataclasses.replace` or keyword args, never positionally. Deck switches keep both fields; new panels start AUTO.
R4 Persistence: both are additive optional panel fields, and `SCHEMA_VERSION` stays 1. Target entry: `{"deck", "preferred_card", "preferred_cards": {...}, "views": {"main", "files"}}`. Each decoder ignores the other's key. Round-trip and legacy tests cover an entry carrying both. A `final` panel decoded to Main (flag off) keeps its `views`.
R5 Engine: after 1b2.11, 1b1's `forced_deck_mode`/`forced_block_mode` early returns live in the generalized deciders (`_decide_document_mode(deck)` and the generic block decider) and read `view_policy(deck)`, which is AUTO for FINAL. 1b1's view-change path (`_apply_main_view_change`, generation counter, pending anchor, spread-target restore) stays Main-only on top of the generic host accessors.
R6 Chrome: the badge appears for Main/Files only. FINAL keeps tab-only title rungs and, with more than 4 tabs, skips the full rungs like Files. `deck_subtitle()` drops `spread` (1b1.4) and gains FINAL's styled `final <glyph>` segment (1b2.14); the two changes are compatible. The rail cue (`page N/M` / `all N`) derives from the host's actual block mode, so FINAL's run-block rail shows it too.
R7 Goldens: 1b2's rule that pre-cutover goldens stay pixel-identical means identical to the master you rebased on, which may already carry 1b1's badge goldens and `agents_deck_view_*`. 1b1 goldens use `ace_final_deck` at its default (off). 1b2.19 re-baselines and inspects every golden its flag removal changes, 1b1's included.
R8 Keys, palette, help, footer: app-level `P` and the picker's `n`/`N` do not collide. Merge help rows, palette commands, footer kwargs and tests with hard-coded deck sets or command counts additively.
R9 Docs: whichever docs phase lands second states the interaction (views are Main/Files only; FINAL always pages automatically, has no badge, and `P` does not apply there) and keeps the two glossary follow-ups consistent (a "Deck View" strand; agent-data-deck lists FINAL).

LAND AGENT: on master, confirm that DeckPanelState keeps `views` and any per-deck preferred cards; that view code dispatches explicitly on Main/Files; that the forced-policy returns and the view-change path survived 1b2.11 if it landed first; and that every 1b1 pilot passes. If 1b2 had already registered FINAL, confirm it shows no badge and `P` is unavailable there, then triage the R1 follow-up.

[2026-09-27T18:49:52Z · sase-1b1.land] LANDING IN PROGRESS (sase-1b1.land, master 372ecc97c3). Not closed: steps 1-2 found remaining epic work, handed to a child plan whose parent_bead is sase-1b1.

VERIFIED: all 7 phases closed and their notes addressed. Commits: 9c4d104aff (model), 12ae3014b9 (main-engine), cb1b5775a0 (files-engine), e75fa98d7b (chrome), a5e2a34dab (controls), c6d68d861e (docs), 5cafbcb53f (verify). 259 epic unit/pilot/catalog tests pass on master. The 6 agents_deck_view_* goldens pass a --check visual run. Cross-epic land checklist:
- DeckPanelState keeps `views` plus per-deck `preferred_cards` (sase-1b2.10).
- Forced-policy early returns survived the sase-1b2.11 extraction: `_decide_document_mode(deck)` and `decide_document_block_mode` in document_blocks.py.
- `_apply_main_view_change` stays Main-only on the generic host accessors.
- Rail cue derives from host block mode.
- FINAL, registered by sase-1b2.14: no badge, P unavailable (test_final_panel_shows_no_badge_and_no_cycle).
- Persistence round-trips both keys.
- `sase bead epic-symbols sase-1b1` lists nothing.

REMAINING EPIC WORK (in the child plan):
(a) Integration fixes made in the landing workspace but NOT committed, because a plan handoff skips the finalizer. The child plan's `integrate` phase re-applies them:
  - 4 keymap tests (test_partial_app_override, test_legacy_commits_action_override_migrates_to_stitches, test_agents_help_uses_configured_direct_visible_fold_selector_key, test_remapped_navigation_key) have failed on master since a5e2a34dab. They remap an action onto "P", which cycle_deck_view now owns, so the registry reverts the override. Confirmed by moving cycle_deck_view off P: all 4 pass. Fix: use the only free uppercase app key, "B".
  - symvision: BlockState, distinct_layouts, layout_signature in view_policy.py are epic-owned unused publics. Privatize them.
  - R2 explicit dispatch in DeckViewPolicies.with_deck and distinct_layouts.
  - Delete the shadowed duplicate view_policy() that 6702105da8 (sase-1b2.11) added to card_documents.py.
  - Add an R4 test: a `final` panel decoded to Main keeps its views.
(b) D10 budgets missed (sase-1b1.6 notes #2-#3). Standard 5k Reply p50 is about 600-700 ms entering page cards or spread (budget 150). The pathological 14k Reply takes 1.4-3.0 s (budget 1 s max). No mitigation or documented guard is in place, so the acceptance checklist is unmet.
(c) The verify live drive (sase screenshot + P / Ctrl+J / | / Z at wide and narrow widths) was never performed (sase-1b1.6 note #4).

FOLLOW-UP TRIAGE (done):
- mypy proposals (1b1.1#2, 1b1.2#2, 1b1.3#3, 1b1.4#3): declined. mypy is clean on master now.
- 1b1.4#4 visual items:
  - top_bar narrow timeouts: +1 sase-18n.
  - output_variables_multi_agent: +1 sase-1bb.
  - axe_chop_run_info_panel: +1 sase-16o (reproduced: setup asserts ChopItem at idx 2, not pixel drift).
  - node_finder_i_hidden nondeterminism: new flake task sase-1bh.
  - header_panel half-page scroll: +1 sase-1b8 (fails on the pre-epic tree too).
- Symvision reds on untouched files (1b1.5#2, 1b1.6#5, 1b1.7#3): non-finalizer symbols +1 sase-1ay. FINAL/finalizer symbols recorded as a DISCOVERED ISSUE on active epic sase-1b2.
- Deck View glossary strand (1b1.7#2): new memory task sase-1bg (R9-consistent).
- Land-agent discoveries:
  - Files Ctrl+J spread pilot flake: +1 sase-1a7 (reproduced on the pre-epic tree).
  - FINAL deck test failures and TUI import count 3405 > 3400 (finalizer_row_state.py pulls sase.finalizers into startup): DISCOVERED ISSUE on sase-1b2.
  - Memory README token drift and 9 test_agent_completion failures from 372ecc97c3: DISCOVERED ISSUE on sase-1bc.
- R1 (extend deck views to FINAL) is still open. Whichever of sase-1b1 / sase-1b2 closes second records it.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1b1.1](sase-1b1.1.md) | Deck view policy model, pure resolution, and persistence | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1b1.2](sase-1b1.2.md) | Main deck honors view policies with anchor-preserving transitions | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1b1.3](sase-1b1.3.md) | Files deck honors view policies with a complete spread probe | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1b1.4](sase-1b1.4.md) | Top-border view badge, rail cue, and subtitle cleanup | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1b1.5](sase-1b1.5.md) | P key, palette view commands, footer, help, and search exits | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1b1.6](sase-1b1.6.md) | View goldens, live inspection, and forced-spread benchmarks | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1b1.7](sase-1b1.7.md) | User docs for deck views | ✓ closed | small | 2026-09-27 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1b1: Deck views: see and choose how a deck panel pages its cards and blocks [in_progress]"]
    n1["sase-1b1.1: Deck view policy model, pure resolution, and persistence [closed]"]
    n2["sase-1b1.2: Main deck honors view policies with anchor-preserving transitions [closed]"]
    n3["sase-1b1.3: Files deck honors view policies with a complete spread probe [closed]"]
    n4["sase-1b1.4: Top-border view badge, rail cue, and subtitle cleanup [closed]"]
    n5["sase-1b1.5: P key, palette view commands, footer, help, and search exits [closed]"]
    n6["sase-1b1.6: View goldens, live inspection, and forced-spread benchmarks [closed]"]
    n7["sase-1b1.7: User docs for deck views [closed]"]
    n8["sase-1b1.8: Deck views landing remainder: integration fixes, P-transition budgets, and the live check [in_progress]"]
    n9["sase-1b1.8.1: Re-apply the sase-1b1 landing integration fixes [closed]"]
    n10["sase-1b1.8.2: Bring P view transitions within the D10 budgets or a measured guard [in_progress]"]
    n11["sase-1b1.8.3: Live wide/narrow drive of deck views and the acceptance checklist [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n8 --> n9
    n8 --> n10
    n8 --> n11
    n1 -.-> n2
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
    n5 -.-> n7
    n9 -.-> n11
    n10 -.-> n11
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.1.md) | [sase-1b1.1](sase-1b1.1.md) | 1 |
| [bbugyi200.athena.sase-1b1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.2.md) | [sase-1b1.2](sase-1b1.2.md) | 1 |
| [bbugyi200.athena.sase-1b1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.3.md) | [sase-1b1.3](sase-1b1.3.md) | 1 |
| [bbugyi200.athena.sase-1b1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b1.4/README.md) | [sase-1b1.4](sase-1b1.4.md) | 1 |
| [bbugyi200.athena.sase-1b1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.5.md) | [sase-1b1.5](sase-1b1.5.md) | 1 |
| [bbugyi200.athena.sase-1b1.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.6.md) | [sase-1b1.6](sase-1b1.6.md) | 1 |
| [bbugyi200.athena.sase-1b1.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.7.md) | [sase-1b1.7](sase-1b1.7.md) | 1 |
| [bbugyi200.athena.sase-1b1.8.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.8.1.md) | [sase-1b1.8.1](sase-1b1.8.1.md) | 1 |
| [bbugyi200.athena.sase-1b1.8.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.8.2.md) | [sase-1b1.8.2](sase-1b1.8.2.md) | 0 |
| [bbugyi200.athena.sase-1b1.8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b1.8.3/README.md) | [sase-1b1.8.3](sase-1b1.8.3.md) | 0 |
| [bbugyi200.athena.sase-1b1.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b1.8.land/README.md) | [sase-1b1.8](sase-1b1.8.md) | 0 |
| [bbugyi200.athena.sase-1b1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.land.md) | [sase-1b1](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9c4d104`](https://github.com/sase-org/sase/commit/9c4d104aff897a02257562a0d3f09fae940c2f5b) | feat(ace-tui): add deck view policy model, pure resolution, and persistence | [sase-1b1.1](sase-1b1.1.md) | 2026-09-27 06:36:19 EDT |
| sase | [`12ae301`](https://github.com/sase-org/sase/commit/12ae3014b97f36e2463e9b11b0101ffcdf52ea5e) | feat(deck-views): main deck honors view policies with anchor-preserving transitions | [sase-1b1.2](sase-1b1.2.md) | 2026-09-27 08:30:32 EDT |
| sase | [`cb1b577`](https://github.com/sase-org/sase/commit/cb1b5775a001c0c8c31aba1cc70d02539e3adba2) | fix(deck-views): declare \_files\_probe\_complete on DeckPanelFilesMixin | [sase-1b1.3](sase-1b1.3.md) | 2026-09-27 08:30:32 EDT |
| sase | [`e75fa98`](https://github.com/sase-org/sase/commit/e75fa98d7b6e9b58e56e7b47f380d10c336bf9dd) | feat(decks): title badge ladder, chrome hold, and block rail cue | [sase-1b1.4](sase-1b1.4.md) | 2026-09-27 10:33:44 EDT |
| sase | [`a5e2a34`](https://github.com/sase-org/sase/commit/a5e2a34dab6b15b1e7c34296fefc637a6410bc69) | feat(deck-views): P cycle, palette view commands, footer/help/search (sase-1b1.5) | [sase-1b1.5](sase-1b1.5.md) | 2026-09-27 11:36:27 EDT |
| sase | [`c6d68d8`](https://github.com/sase-org/sase/commit/c6d68d861ec77d490d160aa859b31fc689614858) | docs(deck-views): document deck views, P cycle, palette, persistence (sase-1b1.7) | [sase-1b1.7](sase-1b1.7.md) | 2026-09-27 12:59:46 EDT |
| sase | [`5cafbcb`](https://github.com/sase-org/sase/commit/5cafbcb53f1b6b9c300cc29c25136eee95abc8d7) | feat(deck-views): verify badges, goldens, and forced-spread benchmarks (sase-1b1.6) | [sase-1b1.6](sase-1b1.6.md) | 2026-09-27 13:10:23 EDT |
| sase | [`67c43d5`](https://github.com/sase-org/sase/commit/67c43d5746db2412d88ca57d4860d00239699a09) | feat(decks): re-apply sase-1b1 landing integration fixes (sase-1b1.8.1) | [sase-1b1.8.1](sase-1b1.8.1.md) | 2026-09-27 15:23:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c.r0][1] | Reviewing the sase-1b1 epic to write a value-added research report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c.r0/README.md

<!-- sase:referenced-by:end -->

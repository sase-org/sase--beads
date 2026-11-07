# Bead: sase-1rq.2.1.5.1.2 — Preserve Reply selection across same-subject delivery

[Bead Pages](../README.md) / [sase-1rq.2.1.5.1](sase-1rq.2.1.5.1.md) / sase-1rq.2.1.5.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.5.md) · **Assignee:** `sase-1rq.2.1.5.1.2` · **Size:** medium
**Created:** 2026-11-07 11:09:42 EST · **Closed:** 2026-11-07 13:25:15 EST
**Plan:** [202611/full\_ci\_remaining\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202611/full_ci_remaining_repairs.md)

## Description

reply-preservation: fix the bounded Main-deck scroll ownership defect tracked by sase-1ln, add a real same-subject delivery regression, and stabilize agents_renamed_generic_session_root_120x40 without hiding user scroll changes or accepting the clamped frame as the golden.

## Notes

[2026-11-07T18:24:46Z · sase-1rq.2.1.5.1.2] PROPOSED FOLLOW-UP: flaky tests/ace/tui/test_agent_archive_reader.py::test_files_dispatch_skips_active_and_workspace_fallback — failed once in the full-suite lane of sase tool run check bd7ec47d977b0bbaec104252b663bc18 (probe_files_deck(missing) returned DeckAvailability(has_content=True, count=2) at line 201, i.e. desired_file_pages state leaking from the first agent in the same test) but passed 2/2 isolated on this tree, 2/2 isolated on the clean base (git stash), and the whole module 3/3 under -n 4; Files-deck code untouched by this phase. No existing bead matched the node or probe_files_deck.

[2026-11-07T18:24:54Z · sase-1rq.2.1.5.1.2] PROPOSED FOLLOW-UP: Python 3.14 import-lock _DeadlockError on sase.core.wait_dependency_resolution._artifact_state during the Agents tab switch (_finalize_agent_list lazy import on the event loop racing a worker-thread import) also hits the AcePage setup of tests/ace/tui/test_main_deck_reply_steal_recovery.py under -n 6 load (2 of ~7 loaded runs failed at expect_state(agent_count, 3) before any Main-deck code ran; serial runs 6/6 green). Already tracked by sase-1qb notes; the old test had identical setup exposure. Fix belongs to the lazy-import owner, not a test sleep.

[2026-11-07T18:24:59Z · sase-1rq.2.1.5.1.2] PROPOSED FOLLOW-UP: FINAL/RECORD spread watchers (card_documents._on_document_scroll_y) derive the stored card from every scroll with no pending-navigation or delivery-hold check, so the same programmatic-landing steal fixed here for Main can affect them; CardDocumentDeliveryHoldMixin is deck-generic but only claimed/honored for DeckId.MAIN in this phase to keep scope bounded.

[2026-11-07T18:25:15Z · sase-1rq.2.1.5.1.2] Fixed sase-1ln root cause (lands via this turn host completion; base 5692321a2e). Mechanism proven by trace: sticky Reply chat-log landing rests above Reply anchor; a same-subject enrichment re-delivery (Context grows with SASE CONTEXT resolving sections, then shrinks) follow-re-lands programmatically and _on_main_scroll_y derived Context (stored=context, view=reply). CI frame of agents_renamed_generic_session_root_120x40 (run 42370668331) was the visual helper re-drive top-aligning Reply at row 2; golden is the correct chat-log landing at row 0. Fix: new decks/delivery_hold.py CardDocumentDeliveryHoldMixin, a token-bound hold claimed by same-subject Main spread re-render (with anchor-relative restore for parked readers, carried across a second delivery) and by sticky/follow landings; Main watcher keeps the held card; released after 2 quiet refresh checks (cap 12), by scroll_to_card/scroll_to_block, new subject, paged mode, or empty doc; derived scrolls now sync the view card (adopt_spread_active). Readiness helper Reply re-drive removed (0 re-drives across full visual suite with fix); delivery hold counts as in-flight. Tests: rewrote tests/ace/tui/test_main_deck_reply_steal_recovery.py (real production-sink deliveries, no helper) + new tests/ace/tui/widgets/decks/test_main_deck_redelivery_hold.py (landed/parked/second delivery/explicit nav supersedes/reader scroll survives/new subject); probes: hold disabled -> 5/6 + full-app fail with stored=context; view sync removed -> reader-scroll test fails. 788 deck+Main tests pass. Visual: full check 1417 passed, 113 drifts of which 110 byte-identical on clean base (sase-1r2.6 heading family etc.), final_rows_60x40 first-attempt flake; 2 goldens encoded the stolen chrome (lone_planner_color, jump_panel_collapsed_single_section; base stored=context/view=reply) and were updated after inspection (scroll unchanged, header Reply). 26 affected nodes/35 goldens check clean first attempt normal + TZ=UTC. sase tool run check: all lint gates pass; full-suite lane 60479 passed, 1 unrelated flake (PROPOSED FOLLOW-UP note).

## Dependencies

- **Blocks:** [sase-1rq.2.1.5.1.4](sase-1rq.2.1.5.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.5.1.2/README.md) | [sase-1rq.2.1.5.1.2](sase-1rq.2.1.5.1.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.2.1.5.1.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.5.1.2/README.md

<!-- sase:referenced-by:end -->

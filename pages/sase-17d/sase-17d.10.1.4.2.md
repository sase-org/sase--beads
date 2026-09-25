# Bead: sase-17d.10.1.4.2 — Migrate the tribe, clan, files, LLM Calls, search and waiting visual tests

[Bead Pages](../README.md) / [sase-17d.10.1.4](sase-17d.10.1.4.md) / sase-17d.10.1.4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17d.10.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.10.1.land.md) · **Assignee:** `sase-17d.10.1.4.2` · **Size:** medium
**Created:** 2026-09-24 17:30:40 EDT · **Closed:** 2026-09-24 22:20:23 EDT
**Plan:** [202609/deck\_cutover\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_cutover_landing_repairs.md)

## Description

tribe-files-visual-migration: migrate the tribe, clan, slow-tools, linked/external repo, LLM Calls, metadata-search and waiting ACE PNG tests listed in section 3.2 onto the deck API, delete the zoom-modal-only waiting scenario, regenerate only their goldens with a scoped just fix-tui-screenshots, and inspect every changed PNG.

## Notes

[2026-09-25T02:19:19Z · 0ru] DONE. Step 3 rows 9-17 migrated: tribe panel four-level (main_deck_scroll in _settle_tribe_visual), swarm clan panel (main_deck_scroll; dropped the '--code' assertion because the compact CLAN MEMBERS jump panel only lists '.family'), slow tools fold ladder (scroll_main_section_to_top slow-tool-calls; deleted dead AgentDetail import, _LLM_CALLS_FOOTER_RE, _rendered_llm_calls_footer and the three legacy scroll helpers), linked-repo diff file panel (Files deck active_scroll; pins paged), commit messages panel (split per deck: Main deck golden agents_commit_messages_panel + new Files deck golden agents_commit_messages_files_panel, because the half-width Main|Files split wraps file names; waits for on-screen text instead of blind ctrl+d; Files title now carries the count so 'files [1/3]' became 'FILES'/'1/3'), external-repo diff (final wait_for_visual_idle + pinned paged; the convergence failure was a missing final idle wait), llm_calls full case (#agent-deck-panel-0-tools-scroll, pinned virtual height re-measured 79 -> 94, stable over 4 runs; zoom_panel_modal.py path string replaced by same-length widgets/decks/main_view.py), metadata search (deck search overlay, focused_panel().search_command()), waiting unknown zoom modal: test and golden deleted. Deviation from the plan: the Wait section and the '[beads] run-bead ◐, done-bead ●, open-bead ○' line live in the identity HEADER above the deck, not in a Main card, so the replacement scenario is test_agents_waiting_unknown_detail_header_png_snapshot (press d to expand the header) with golden agents_waiting_unknown_header_200x40 (200 columns because the header is unreadable at 120); tokens are asserted individually since the line wraps. Optional clean-ups done: zoom fixtures docstring, ' · view:' split in proc_shells.

[2026-09-25T02:20:23Z · 0ru] Remaining nine visual test migrations done (waiting unknown zoom modal test and golden deleted, replaced by a header scenario); all pass under the final full --check.

## Dependencies

- **Blocks:** [sase-17d.10.1.4.3](sase-17d.10.1.4.3.md) ✓ · ⧖ 2026-09-24

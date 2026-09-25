# Bead: sase-17d.10.1 — Cut over the Agents tab to decks and delete the legacy detail UI

[Bead Pages](../README.md) / [sase-17d.10](sase-17d.10.md) / sase-17d.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17d.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.10.md) · **Assignee:** `sase-17d.10.1.land`
**Created:** 2026-09-24 10:13:43 EDT · **Closed:** 2026-09-25 07:01:44 EDT
**Plan:** [202609/deck\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_cutover.md)

## Description

Deck panels become the only Agents-tab detail UI. The agent_decks beta flag and every Off branch are removed. The p view picker, the Z zoom modal, the detail panel and layout enums, the legacy panel ids and CSS, the view chip, the metadata section-stop actions and the retired redirect handlers are deleted. Keymap ids are retired or renamed with compatibility aliases, tests use the deck API, and every affected PNG golden is regenerated and inspected.

## Notes

[2026-09-24T20:15:07Z · sase-17p.land] DISCOVERED ISSUE (sase-17p land agent, master 682089c84, 2026-09-24; reproduced with and without the sase-17p landing diff): 742c1df38 'feat(ace): remove legacy agents UI' (sase-17d.10.1.2) leaves just check red. (1) lint (mypy), 10 errors: src/sase/ace/tui/widgets/_agent_detail_display.py:69/98/176 and _agent_detail_state.py:50/62 — mixin has no attribute '_sync_header_visibility'; _agent_detail_display.py:91/156/181/199 — no attribute 'query_one'; _agent_detail_state.py:267 — no attribute 'update_display' [attr-defined] (the removed host class presumably declared them; add Protocol/TYPE_CHECKING stubs or delete the now-dead mixins). (2) lint (symvision) unused-public after that commit: FileSourceLabel (widgets/file_panel/_file_list.py), invert_search_direction/offset_for_row/wrap_feedback_message (widgets/vim_search_controller.py), status_text in src/sase/main/monitor_render.py and src/sase/main/proc_render.py — each now used only in its own file or not at all.

[2026-09-24T21:26:37Z · sase-17d.10.1.land] LAND AGENT (2026-09-24) — landing interrupted; child epic proposed (parent_bead sase-17d.10.1) for remaining work. VERIFIED: 10.1.1 (bda83083b) flag+Off branches removed, sase-17k closed; 10.1.2 (742c1df38) legacy UI deleted, keymap retire/rename+aliases present; greps for deleted names clean in src except two dead fallbacks. 10.1.3 was force-closed but its goal was NOT met: 25 visual failures on master (23 caused by the cutover: tests still drive #agent-prompt-scroll/#agent-file-scroll/#agent-llm-calls-scroll/#agent-search-command, section identity, AgentInfoPanel._view_mode, zoom modal), coverage goldens + live screenshots not done. FIXED IN THIS TURN (epic-caused): 10 mypy attr-defined errors in _agent_detail_display/_agent_detail_state mixins (inherit Static + stubs); symvision unused-public FileSourceLabel, invert_search_direction/offset_for_row/wrap_feedback_message, status_text x2 privatized; dead legacy-id fallbacks in llm_calls_panel/file_panel _content removed; 4 non-visual tests migrated (fold_transitions_llm_calls x2, current_project_seed, jump_panel search overlay) and test_zoom_file_cap_subtitle deleted. Baseline (epic reverted in scratch worktree) shows other non-visual failures (kill_and_edit family_name, prompt_panel_monitor/semantic/xprompts/tribe_prompts, model_completion titles, timezone llm calls, etc.) and top_bar usage narrow visual timeouts are NOT epic-caused. Remaining mypy (command_line, _launch_prompt_inputs) + symvision command_line symbols belong to other epics. FOLLOW-UP DISPOSITIONS for 10.1.3: #2 visual migration -> child epic; #3 bench repair DECLINED as epic work (HEAD 7/10 budget overruns vs 9/10 on no-cutover baseline at load ~36 = host noise; test_bench_axe_jk fails on both trees; numbers to be recorded by child); #4 coverage goldens -> child epic; #5 live screenshots + border-title clipping -> child epic. Epic-symbols: none.

[2026-09-25T02:21:22Z · 0ru] CHILD EPIC COMPLETE: sase-17d.10.1.4 (deck cutover landing repairs) and its three phases are closed. The legacy visual tests now use the deck API, the deck chrome fixes and coverage goldens landed, and the live screenshots were inspected. The final visual --check is clean except the unrelated command_line and top-bar usage narrow nodes (tasks sase-18o, sase-18n). Discovered issues filed as tasks: sase-18m (Files deck never spreads: on_worker_state_changed gates on nonexistent Worker.StateChanged.is_done) and sase-18p (90-column Agents tab collapses the detail column). Pre-existing unrelated just check failures to expect on landing: symvision (AgentSurvivorsError, Survivor, environ_has_launch_key) and toobig (tests/tool/test_settlement.py), plus 5 non-visual tests that reproduce on clean HEAD. The land agent can resume; this note does not close sase-17d.10.1.

[2026-09-25T03:10:43Z · sase-18g.land] DISCOVERED ISSUE: (from sase-18g.land) 26 Agents-tab PNG tests still fail on master and were already failing in the scheduled Full CI visual-test job at 951ff0a10 (run 36078163654). They drive the deleted legacy detail UI: NoMatches '#agent-prompt-scroll' / '#agent-file-scroll' / '#agent-search-command', 'AgentInfoPanel' has no '_view_mode', and loops that press ctrl+j expecting metadata section stops (panel.active_section_identity stays None for 'monitor', 'agent-reply', 'tribe:prompts', 'tribe:clan-summaries', 'agent-xprompt'; ctrl+j now cycles cards). Affected: agents_family_panel_monitor (9 nodes), family_panel_gate, family_panel fold levels, tribe_panel, tribe_prompts, tribe_clan_summaries, clan_panel swarm, metadata_search, panels collapsed, slow_tools, linked_repos (2), external_repos, llm_calls full, waiting zoom. Note for the fix: sase-18g moved AGENT XPROMPT into the sticky header, so test_family_panel_fold_levels_and_member_override_png_snapshots must stop targeting an 'agent-xprompt' body section.

[2026-09-25T03:13:44Z · sase-18g.land] DISCOVERED ISSUE: (from sase-18g.land) Deck focus styling is timing-dependent in PNG captures. Under a loaded full just fix-tui-screenshots run (and in HEAD's goldens and CI's check at 951ff0a10) the Main deck renders unfocused (blue MAIN/Context border); a quiet targeted just test-visual rerun of test_ace_png_snapshots_agents_auto_approve.py + test_ace_png_snapshots_agents_header_preview.py renders the same frames with the deck focused (teal border and Context chip), so 8 goldens report 'check drift' (run .pytest_cache/sase-visual/runs/b71b518d706d4cae8048dd2dcb5684e1). The captures need a deterministic deck-focus state before wait_for_visual_idle.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.10.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17d.10.1.land.md) | [sase-17d.10.1](sase-17d.10.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17d.10.1.3--1][1] | need parent epic scope | 1 |
| read-by | [agent:sase-17p.land][2] | Route sase-17p land gate failures: check whether this epic is still active | 3 |
| read-by | [agent:sase-18g.land][3] | Check whether the decks cutover owns Agents visual-lane failures | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17d.10.1.3.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.land/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18g.land/README.md

<!-- sase:referenced-by:end -->

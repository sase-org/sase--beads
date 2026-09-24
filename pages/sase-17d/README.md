# Bead: sase-17d — Agents tab agent data decks and cards

[Bead Pages](../README.md) / sase-17d

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qd.md) · **Assignee:** `sase-17d.land`
**Created:** 2026-09-23 19:16:45 EDT
**Plan:** [202609/agents\_tab\_decks\_and\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_decks_and_cards.md)

## Description

The Agents tab replaces its metadata panel and its Files and LLM Calls panels with one deck-panel type. It shows one or two panels, stacked top and bottom or side by side, and each panel shows an agent data deck (Main, Files or Tools) made of agent data cards. A deck renders all of its cards on one page when they fit a configurable threshold and one card per page otherwise. Keys cycle cards (Ctrl+J/K) and decks (Ctrl+N/P), split and unsplit panels (\ and |), move focus (Ctrl+F), collapse the node panel (Ctrl+S) and zoom a deck in place (Z). The p view picker, the Z zoom modal and the legacy panel modes are deleted, and glossary strands describe the new vocabulary.

## Notes

[2026-09-24T02:22:32Z · chop.refresh_docs.sase.1_365885.1] DISCOVERED ISSUE: just check fails at lint (mypy) on master 00ee51996 (deck panel core): src/sase/ace/tui/widgets/file_panel/_content.py:132 error: "FilePanelContentMixin" has no attribute "parent" [attr-defined] in _get_scroll_container. Reproduced from a docs-only working tree via sase tool run 6476c6ba9891284bb1887d7baabfef64. Also: with agent_decks on, no keys switch decks/cards yet, so the Reply card is unreachable (docs now state this).

[2026-09-24T14:16:11Z · sase-17d.8.f0.f0] LAND INSTRUCTION (from user) — sase-17d.8 (deck-spread-mode) was closed by hand, but its verification and close-out were never finished. That remaining work is in scope for this epic. The land agent MUST complete it before closing sase-17d. Do NOT turn any of these items into task beads. This includes sase-17d.8 PROPOSED FOLLOW-UP notes #1–#3, which are this same work. The spec is plan:202609/deck_spread_mode.md §9 (goldens), §10 (perf) and §11 (close-out).

1. toobig (MASTER IS RED): src/sase/ace/tui/widgets/decks/panel.py is 1051 lines and over the 1000 hard limit. `toobig src 1000 850 700` fails on master at 12b253c35. It grew past 1000 when 17d.8 was rebased onto 17d.9's persistence change. Move the remaining spread/Files-probe orchestration from panel.py into panel_spread.py, and any other cohesive chunk into a mixin. Keep DeckPanel's public API unchanged. The plan targets ~500 lines per module. First check whether sase-17d.10 (legacy UI deletion) already shrank the file.
2. PNG goldens: tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py has none for spread mode. Add three per §9: spread Main, spread Files, and a paged-after-threshold Main deck. Generate them with a targeted `just fix-tui-screenshots -- <selectors>` and open and inspect every PNG. Do not churn the existing paged goldens, which are pinned to spread_max_screens=0.
3. Live screenshots: with SASE_FEATURE_FLAGS='{"agent_decks": true}', use `sase screenshot` to capture (a) single-panel spread Main, (b) a split with one spread panel and one paged panel, and (c) spread Files. Inspect the separator styling (blank line + titled rule, single-row meta, tiny-width degrade), check that the title pill follows the scroll-derived active card, and fix any defects you find.
4. Perf: run `SASE_TUI_PERF=1 pytest -s -m slow tests/ace/tui/bench_tui_jk.py` through the guarded runner (see lint_and_test memory). Run it with the flag on, in SINGLE and LEFT_RIGHT layouts, on the parent of 329d4049b and on the current tree. p95 must stay under 16 ms. 17d.8 hit 6 bench failures in its environment and recorded no numbers. Find out why: an env problem gets fixed or worked around, and a regression gets fixed. Record the before and after p95 in the epic close note.
5. Symvision: `just check` must pass clean. 17d.8 reported pre-existing private-import failures unrelated to decks, so re-run it on the final tree. Fix anything the epic introduced. If anything unrelated is still red, report it with evidence instead of calling it verified.

Done when: `just check` is green (toobig included), the three goldens are committed and inspected, the live screenshots are inspected, and the bench numbers are in the close note. Only then close sase-17d.

[2026-09-24T15:39:26Z · sase-17m.3.1.land] DISCOVERED ISSUE (sase-17m.3.1 land agent, master 77e0cfb6c, 2026-09-24): 9 deterministic unit-test failures trace to this epic's phases and also fail on the pre-agent-session tree bb81b993a^. (1) sase-17d.2 (9abf08b5d, card-partitioned Main documents) makes the prompt panel emit CardPart wrappers that the test helpers do not unwrap: tests/ace/tui/widgets/test_agent_prompt_panel_monitor.py (test_monitor_section_dims_the_inactive_status_half, test_family_monitor_phase_decodes_ansi_and_drops_escapes, test_starter_monitor_phase_decodes_ansi_and_drops_escapes), test_agent_prompt_panel_steps.py::test_parallel_step_does_not_show_agent_prompt, test_agent_prompt_panel_xprompts.py::test_update_display_renders_xprompts_after_detail_settles, and test_agent_prompt_semantic.py (test_agent_xprompt_and_prompt_receive_roles_replies_do_not, test_hint_mode_restores_file_hints_after_semantics, test_family_pinned_and_workflow_authored_prompt_paths). Each fails with an AssertionError such as 'isinstance(CardPart(card_id=context...), (Text, AgentHeaderRenderable))' or 'TESTING not found in rendered monitor section'. (2) sase-17d.1 (9c701d658) added subject_identity=agent.identity in AgentLLMCallsPanel._cached_fetch_result, so tests/test_timezone_display_tui.py::test_llm_calls_panel_fallbacks_use_configured_wall_time fails with AttributeError: SimpleNamespace has no attribute 'identity'. Evidence: sase tool run test 09a0fb945e88.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-17d.1](sase-17d.1.md) | LLM Calls stale-worker fix and split-key display | ✓ closed | small | 2026-09-23 | 1 | 1 |
| [sase-17d.10](sase-17d.10.md) | Cut over to decks and delete the legacy UI | ◐ in_progress | large | 2026-09-23 | 1 | 0 |
| [sase-17d.11](sase-17d.11.md) | Docs, glossary strands and key-change notice | ◐ in_progress | medium | 2026-09-23 | 1 | 0 |
| [sase-17d.2](sase-17d.2.md) | Card-partitioned Main documents | ✓ closed | large | 2026-09-23 | 1 | 1 |
| [sase-17d.3](sase-17d.3.md) | Deck panel core behind the agent\_decks beta flag | ✓ closed | large | 2026-09-23 | 1 | 1 |
| [sase-17d.4](sase-17d.4.md) | Card and deck cycling keys | ✓ closed | medium | 2026-09-23 | 0 | 0 |
| [sase-17d.5](sase-17d.5.md) | Split layouts, focus and split ratio | ✓ closed | large | 2026-09-23 | 1 | 1 |
| [sase-17d.6](sase-17d.6.md) | Retarget detail actions to the focused deck panel | ✓ closed | large | 2026-09-23 | 1 | 1 |
| [sase-17d.7](sase-17d.7.md) | Node panel collapse and in-place zoom | ✓ closed | medium | 2026-09-23 | 1 | 1 |
| [sase-17d.8](sase-17d.8.md) | Spread versus paged rendering | ✓ closed | large | 2026-09-23 | 1 | 1 |
| [sase-17d.9](sase-17d.9.md) | Persist the deck layout across restarts | ✓ closed | small | 2026-09-23 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-17d: Agents tab agent data decks and cards [in_progress]"]
    n1["sase-17d.1: LLM Calls stale-worker fix and split-key display [closed]"]
    n2["sase-17d.10: Cut over to decks and delete the legacy UI [in_progress]"]
    n3["sase-17d.10.1: Cut over the Agents tab to decks and delete the legacy detail UI [in_progress]"]
    n4["sase-17d.10.1.1: Remove the agent_decks flag and its Off branches [closed]"]
    n5["sase-17d.10.1.2: Delete the legacy detail UI and retire its keymap ids [in_progress]"]
    n6["sase-17d.10.1.3: Regenerate and inspect every affected PNG golden [in_progress]"]
    n7["sase-17d.11: Docs, glossary strands and key-change notice [in_progress]"]
    n8["sase-17d.2: Card-partitioned Main documents [closed]"]
    n9["sase-17d.3: Deck panel core behind the agent_decks beta flag [closed]"]
    n10["sase-17d.4: Card and deck cycling keys [closed]"]
    n11["sase-17d.5: Split layouts, focus and split ratio [closed]"]
    n12["sase-17d.6: Retarget detail actions to the focused deck panel [closed]"]
    n13["sase-17d.7: Node panel collapse and in-place zoom [closed]"]
    n14["sase-17d.8: Spread versus paged rendering [closed]"]
    n15["sase-17d.9: Persist the deck layout across restarts [closed]"]
    n0 --> n1
    n0 --> n2
    n2 --> n3
    n3 --> n4
    n3 --> n5
    n3 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n0 --> n11
    n0 --> n12
    n0 --> n13
    n0 --> n14
    n0 --> n15
    n1 -.-> n9
    n2 -.-> n7
    n4 -.-> n5
    n5 -.-> n6
    n8 -.-> n9
    n9 -.-> n10
    n10 -.-> n11
    n11 -.-> n12
    n11 -.-> n13
    n12 -.-> n14
    n13 -.-> n15
    n14 -.-> n2
    n15 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.1/README.md) | [sase-17d.1](sase-17d.1.md) | 1 |
| [bbugyi200.athena.sase-17d.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.10.md) | [sase-17d.10](sase-17d.10.md) | 0 |
| [bbugyi200.athena.sase-17d.10.1.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.10.1.1.md) | [sase-17d.10.1.1](sase-17d.10.1.1.md) | 1 |
| [bbugyi200.athena.sase-17d.10.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.10.1.2.md) | [sase-17d.10.1.2](sase-17d.10.1.2.md) | 1 |
| [bbugyi200.athena.sase-17d.10.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.10.1.3/README.md) | [sase-17d.10.1.3](sase-17d.10.1.3.md) | 0 |
| [bbugyi200.athena.sase-17d.10.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.10.1.land/README.md) | [sase-17d.10.1](sase-17d.10.1.md) | 0 |
| [bbugyi200.athena.sase-17d.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.11/README.md) | [sase-17d.11](sase-17d.11.md) | 0 |
| [bbugyi200.athena.sase-17d.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.2.md) | [sase-17d.2](sase-17d.2.md) | 1 |
| [bbugyi200.athena.sase-17d.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.3.md) | [sase-17d.3](sase-17d.3.md) | 1 |
| [bbugyi200.athena.sase-17d.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.5.md) | [sase-17d.5](sase-17d.5.md) | 1 |
| [bbugyi200.athena.sase-17d.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.6.md) | [sase-17d.6](sase-17d.6.md) | 1 |
| [bbugyi200.athena.sase-17d.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.7/README.md) | [sase-17d.7](sase-17d.7.md) | 1 |
| [bbugyi200.athena.sase-17d.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.8.md) | [sase-17d.8](sase-17d.8.md) | 1 |
| [bbugyi200.athena.sase-17d.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.9/README.md) | [sase-17d.9](sase-17d.9.md) | 1 |
| [bbugyi200.athena.sase-17d.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.land/README.md) | [sase-17d](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9c701d6`](https://github.com/sase-org/sase/commit/9c701d658fef3edcef2981da5c09058ae0844ad1) | fix(tui): guard LLM Calls panel against stale-worker paints; split-key display | [sase-17d.1](sase-17d.1.md) | 2026-09-23 19:36:21 EDT |
| sase | [`9abf08b`](https://github.com/sase-org/sase/commit/9abf08b5df74ebc17f5e293e4909702867105880) | feat(agents-tab): card-partitioned Main documents | [sase-17d.2](sase-17d.2.md) | 2026-09-23 20:09:06 EDT |
| sase | [`00ee519`](https://github.com/sase-org/sase/commit/00ee51996d109f2715701b4140f7b528520764de) | feat(agents-tui): deck panel core behind the agent\_decks beta flag | [sase-17d.3](sase-17d.3.md) | 2026-09-23 21:30:43 EDT |
| sase | [`075225d`](https://github.com/sase-org/sase/commit/075225d53795b20eb18dd4a8f32a421ebaa8caad) | feat(ace): implement deck splits focus layout state machine | [sase-17d.5](sase-17d.5.md) | 2026-09-24 08:27:07 EDT |
| sase | [`71fff39`](https://github.com/sase-org/sase/commit/71fff39d1588bd96ded18c7f5b64c1ca9d63421e) | feat(ace-tui): deck node collapse and in-place zoom | [sase-17d.7](sase-17d.7.md) | 2026-09-24 09:13:00 EDT |
| sase | [`7d22725`](https://github.com/sase-org/sase/commit/7d2272588839582b01bcdeb789a26708ed0f1b8d) | feat(ace): retarget agents detail actions to focused deck panel | [sase-17d.6](sase-17d.6.md) | 2026-09-24 09:17:42 EDT |
| sase | [`4388817`](https://github.com/sase-org/sase/commit/43888178618aa31fb531a3d02e0ffb4fe6839dc7) | feat(agents): persist deck layout across restarts | [sase-17d.9](sase-17d.9.md) | 2026-09-24 09:47:52 EDT |
| sase | [`329d404`](https://github.com/sase-org/sase/commit/329d4049b6f61467f5a97006346f0b487b994ee8) | feat(ace): implement deck spread versus paged rendering (sase-17d.8) | [sase-17d.8](sase-17d.8.md) | 2026-09-24 09:53:14 EDT |
| sase | [`bda8308`](https://github.com/sase-org/sase/commit/bda83083bfec4fa0cc0d8ddbebc7f764f56ac1c8) | test(ace): drop zoom-modal routing tests and migrate persistence/metadata tests after deck flag removal | [sase-17d.10.1.1](sase-17d.10.1.1.md) | 2026-09-24 13:23:32 EDT |
| sase | [`742c1df`](https://github.com/sase-org/sase/commit/742c1df38b04d1b190a5102168f0cf2ab37e6840) | feat(ace): remove legacy agents UI | [sase-17d.10.1.2](sase-17d.10.1.2.md) | 2026-09-24 14:37:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0ql][1] | Understand sase-17d epic scope to generate infographic | 1 |
| read-by | [agent:sase-17d.7][2] | parent status | 1 |
| read-by | [agent:sase-17d.9][3] | parent epic plan for deck persistence context | 1 |
| read-by | [agent:sase-17m.2.1.land][4] | Check existing notes for the mypy issue | 2 |
| read-by | [agent:sase-17m.3.1.land][5] | Check whether decks/panel.py toobig and agent_decks flag-lint failures are already tracked by this epic | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.0ql/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.7/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.9/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.land/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.land/README.md

<!-- sase:referenced-by:end -->

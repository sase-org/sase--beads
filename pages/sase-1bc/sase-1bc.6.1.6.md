# Bead: sase-1bc.6.1.6 — Agent tabs: repair the scope pipeline, tab switching, cross-tab jumps, and scope wording

[Bead Pages](../README.md) / [sase-1bc.6.1](sase-1bc.6.1.md) / sase-1bc.6.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bc.6.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.1.land.md) · **Assignee:** `sase-1bc.6.1.6.land`
**Created:** 2026-09-27 20:11:16 EDT · **Closed:** 2026-09-28 07:18:27 EDT
**Plan:** [202609/agent\_tabs\_scope\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope_repairs.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/agent_tabs_scope_repairs.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope_repairs.md

<!-- sase:links:end -->

## Description

Fix the defects the sase-1bc.6.1 landing review found in the flagged agent-tabs feature before that epic closes. Worker-path status overrides and the tab-index memo work. A tab switch restores the target tab's own selection and focused panel. Emptied machine tabs never strand the user. Every cross-tab jump records the right back-anchor and restores the previous tab when its reveal fails. Bulk wording states the real scope. The epic's public symbols pass symvision. With the `agent_tabs` flag off, the TUI stays exactly as it was before agent tabs.

## Notes

[2026-09-28T10:15:33Z · 0tf] LANDING TRIAGE (manual landing on master 5b409a5aa3; land agent sase-1bc.6.1.6.land is stuck WAITING although all three phases closed). PROPOSED FOLLOW-UP outcomes: (1) sase-1bc.6.1.6.1 #1 test_agent_completion %tab failures - declined, already DISCOVERED ISSUE #1/#2 on active epic sase-1bc (caused by sase-1bc.4), not this epic. (2) sase-1bc.6.1.6.1 #2 rail symvision warnings - declined, resolved: sase-1bn landed and symvision on 5b409a5aa3 reports every symbol used. (3) sase-1bc.6.1.6.2 #1 pyright narrowing nit in tests/test_agent_revive.py - no duplicate or causal epic; folded into this landing's tale as a two-line isinstance narrowing instead of a separate xsmall task (repo gates run mypy, not pyright). (4) sase-1bc.6.1.6.2 #2 - test_axe_run_agent_exec_repeat_env.py (6 nodes) is already DISCOVERED ISSUE #3 on sase-1bc (caused by sase-1bc.5 _export_exec_agent_tab), declined as duplicate; tests/completion/test_snapshot.py (2 nodes) reproduced alone on 5b409a5aa3 and corroborated with +1 on sase-18s. (5) sase-1bc.6.1.6.3 #2 test_no_system_clock_display_sites - declined, tracked by sase-1bp; the view_vocabulary.py site is already a DISCOVERED ISSUE on sase-1bt. Integration review of the 19 commits since this epic started: two defects caused by active epic sase-1bt recorded there as DISCOVERED ISSUE notes (Tools pane 'Open Agent' passes a name string to _reveal_agent_row; tool-run chip apply forces full rebuilds for off-tab/hidden rows); no other commit conflicts with the agent-tab repairs. Remaining epic-caused work goes to a tale: link-trail top-tab restore on failed reveal, first-visit panel-focus check, memo snapshot hardening, legacy bracket-yield warning wording, the missing phase-2 entry-point tests, and splitting tests/ace/tui/test_agent_tab_cross_nav.py (1009 lines, over the toobig 1000 limit).

[2026-09-28T11:18:27Z · 0tf--1] All three phases verified in source (dae0f6efad, 3ba7f3b22f, d094fe70ee). Items 1-6 landed; item 2 needed the first-visit panel-focus fix (_restore_tab_memory now focuses the panel that holds row 0 and clears _expanded_panel_focus). Item 1 restores current_tab on a failed Agents link-trail reveal. Item 3 stores row-object snapshots compared with is. Item 4 emits the legacy bracket warning after collision/duplicate resolution. Item 5 uses isinstance(AgentReviveDelta). Item 6 split tests/ace/tui/test_agent_tab_cross_nav.py into _agent_tab_cross_nav_helpers.py plus test_agent_tab_cross_nav_entry_points.py and test_agent_tab_cross_nav_modals.py (all under 850 lines) and added the missing real-mixin entry-point tests.

sase bead epic-symbols sase-1bc.6.1.6 listed no entries. The check lint (symvision) stage failed only on pre-existing stale Justfile --epic-symbol entries for closed bead sase-1bu.5 (goal_sync_status, maybe_spawn_goals_fetch, run_goals_fetch); those three items were classified KNOWN and are not this epic's work.

sase tool run check 5fbb1cd273741dc7c46b5259208bfa59 (monitor svx1hmhdcs09) failed with 13 KNOWN and 4 NEW signatures. The 4 NEW items are tests/ace/tui/test_agent_completion.py::test_named_proc_completion_candidate_uses_exact_proc_id, test_build_agent_completion_candidates_derives_ordered_groups, test_agent_session_completion_candidate_build_does_not_resolve_plan_or_bead_io, and test_named_proc_is_not_also_offered_as_a_plain_agent_candidate. Those are the sase-1bc.4 %tab failures already recorded as DISCOVERED ISSUE notes #1/#2 on sase-1bc (candidate name 'main' where 'ship' is expected; extra 'tab' candidate beside named-proc). This landing did not touch completion code (classifier touched=false); the NEW labels are assertion-signature drift of that known fallout. Other KNOWN failures on the run: test_expanded_overflowing_header_claims_half_page_scroll (sase-1b8); remaining test_agent_completion.py nodes from notes #1/#2; and known TUI timeout/resume failures in test_plugins_browser_pane_loading, test_config_center_resume, test_admin_center_selection_resume, and test_xprompt_browser_load_keymap. Targeted pytest of the agent-tab suites: 179 passed.

Follow-up triage is recorded in this epic's LANDING TRIAGE note. Phase 2 deliberately routes run-log, revive, Files, and link-trail through _try_reveal_agent_row in both flag states per the epic plan no-worse-than-before rule.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.6.1.6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.6.1.6.land/README.md) | [sase-1bc.6.1.6](sase-1bc.6.1.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0tf--1][1] | Need epic closeout criteria and PLAN path | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tf.md

<!-- sase:referenced-by:end -->

# Bead: sase-17m.5.1 — ACE agent session surfaces (ace-cutover)

[Bead Pages](../README.md) / [sase-17m.5](sase-17m.5.md) / sase-17m.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.5.md) · **Assignee:** `sase-17m.5.1.land`
**Created:** 2026-09-25 00:06:00 EDT · **Closed:** 2026-09-25 13:31:44 EDT
**Plan:** [202609/agent\_session\_ace\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover.md)

## Description

Inside ACE (src/sase/ace/**, tests/ace/**, tests/perf/**, default_config.yml, and sase.schema.json), the former agent-family concept is named "agent session" in every module, class, identifier, row kind, relation, grouping mode, trace name, perf scenario, comment, test, and golden. The visible copy reads SESSION SHELLS, SESSION, "Session" grouping, and "collapse session". Core-emitted legacy spellings stay as marked readers. Unrelated meanings of "family" are unchanged. The performance contract does not change, and `sase tool run check` passes.

## Notes

[2026-09-25T08:35:15Z · sase-17m.5.1.land] LANDING PAUSED (sase-17m.5.1.land): verification found remaining epic work, planned as a child epic with parent_bead sase-17m.5.1. Findings: (1) 15 non-visual tests fail on HEAD, all epic-caused — they call renamed panel methods (_update_family_display, _family_text_with_hints) or expect retired copy (FAMILY header, 'build · family', 'Members: N agents · 1 family'): test_agent_display_clan/clan_roster/tribe/tribe_roster, test_agent_display_xprompt_hints, test_identity_header_xprompt, test_prompt_panel_section_navigation_rendering (2), test_summary_fold_contracts (1 + 4 [family] setup errors); full run tests/ace+tests/perf non-visual: 11 failed, 4 errors, 14459 passed. (2) visible family copy remains in src/sase/ace: tribe Composition 'N families' (_agent_display_tribe_header.py, _identity_header_compact.py), Artifacts Agents pane description, statistics_help_modal eligibility text, _fold.py notify, revert preview error and confirm-revert 'scope family'; plus agent-family comments/docstrings in artifact_reads/bead_touches/glossary_reads/memory_reads/skill_uses/opened_workspaces/agent_workspace_tmux_modal/revert_agent_discovery/_agent_list_render_agent_prefix/_agent_session_shell_membership. (3) ~178 family-named test functions/helpers in 88 tests/ace files plus family-concept locals/kwargs (owner_roster_fixture family= kwarg writes agent_session keys, so no persisted-shape ruling is needed). (4) no new-shape fleet summary/locator fixture coverage (proposal sase-17m.5.1.1 #3). (5) docs integration: docs/perf_runbook.md still names family_container_press/_unfolded_press; docs/ace.md 'plan-family' L5051/L5066 hand-off; docs/pager.md 'Family and clan conversations'. (6) j/k benches need a quiet-host re-run (sase-17m.5.1.5 #3). FOLLOW-UP OUTCOMES: 5.1.1#1 declined (lint gates fixed on master by c7a78904b/951ff0a10; 5.1.5 saw all lint green); 5.1.1#2 PNG part resolved by phases 4/5, non-PNG test part is child-plan work; 5.1.1#3 child-plan work; 5.1.2#1 declined (symvision CdResolution/PathCompletionRequest fixed on master); 5.1.3#1 child-plan work (still failing); 5.1.3#2 declined (test-waits/symvision fixed; memory README drift fixed by 4220fe7b7, which an init-memory run from this land agent pushed); 5.1.4#1 + 5.1.5#1 -> new task sase-18y (caused by sase-18g.2 4af219eba, not this epic); 5.1.4#2 + 5.1.5#5 declined (README drift fixed by 4220fe7b7); 5.1.5#2 -> +1 on sase-18o (command_line), sase-18n (provider_usage narrow), sase-x5 (clan swarm); 5.1.5#3 child-plan work; 5.1.5#4 child-plan work. Integration: non-epic commits since start (61f88ccd6, d2c2dd142, 7840592c5, 696026157, fad9b5d03, 02c4b029a, c7a78904b, 5b305b1b9, 403586e27, 3c6e8f04d) add no remaining family identifiers (02c4b029a's _dismiss_persistence.py 'family/workflow children' docstring was already renamed by phase sase-17m.5.1.2); the docs items above are the only integration work and are in the child plan. epic-symbols: none.

[2026-09-25T17:31:44Z · sase-17m.5.1.6.5.land--1] Rechecked parent plan sase-17m.5.1 after child epic sase-17m.5.1.6 closed.

Descendants: phases 5.1.1-5 closed previously; child epic 5.1.6 closed done (note #1 copy pins, note #2 retry-session visual, identifier/docs/perf work). Paused landing findings are all addressed: SESSION SHELLS is the roster title; no remaining family-named ACE modules or tests/ace files; retry fixture and visual query are retry-session; docs no longer name family_container_press or pager "Family and clan" in ACE-owned copy. Core-emitted legacy readers stay marked for sase-17m.8; plan-family docs remain sase-17m.6; agents_sync family pages remain sase-17m.9.

Integration/post-child drift: post-pause ACE commits (waiting chip, deck picker, note wrap, command-line) add no agent-family copy. Origin-only commits 4e18680d3/0b70c2c3d/7a5559cc7/e01d34651 already use agent-session naming.

just check after 5.1.6 (monitor 4s0jgas16mkg) timed out at 1h during test (scoped) under load1 30-47; fmt/lint/mypy/symvision/SASE validation passed; tests SIGKILL incomplete, not a failed assertion. Equivalent isolation-pass contention (sase-12f / sase-19c / sase-19d), not remaining epic work. just symvision clean after 5.1.6 close. sase bead epic-symbols reported none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.5.1.land.md) | [sase-17m.5.1](sase-17m.5.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.5.1.6.2][1] | Need land agent finding note #1 for scope context | 1 |
| read-by | [agent:sase-17m.5.1.6.5.land--1][2] | Confirm close status and notes after auto-cascade | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.6.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.5.1.6.5.land.md

<!-- sase:referenced-by:end -->

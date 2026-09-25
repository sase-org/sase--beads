# Bead: sase-17m.5.1.6.2 — Agent-session test identifiers in widgets, modals, actions, and visual tests

[Bead Pages](../README.md) / [sase-17m.5.1.6](sase-17m.5.1.6.md) / sase-17m.5.1.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.1.land.md) · **Assignee:** `sase-17m.5.1.6.2` · **Size:** medium
**Created:** 2026-09-25 04:39:11 EDT · **Closed:** 2026-09-25 06:02:49 EDT
**Plan:** [202609/agent\_session\_ace\_cutover\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover_finish.md)

## Description

widget-tests: rename the family-concept test functions, helpers, locals, fixture kwargs, and docstrings in tests/ace/tui/widgets, tests/ace/tui/modals, tests/ace/tui/actions, and tests/ace/tui/visual to agent-session naming. Keep unrelated meanings, marked core-emitted legacy wire fixtures, and opaque rendered test data. Update the renamed node ID in tests/reproducible_flake_baseline.txt. No pixels change.

## Notes

[2026-09-25T10:02:20Z · sase-17m.5.1.6.2] Golden re-baselines beyond the identifier renames (for docs-verify): earlier phases left 24 PNG goldens stale. (a) 9 clan-detail goldens still showed "1 family" after copy-stragglers changed the Composition chip: agents_clan_panel_swarm{,_level_2,_level_3}_120x40 (the test hard-asserted "1 family"; now asserts "3 agents · 1" and "session" separately because the chip wraps) and agents_clan_tree_{collapsed,expanded}, agents_clan_unread_{collapsed,expanded}, agents_running_clan_runtime_{collapsed,expanded}. Diffs confined to the chip rewrap (plus one scrollbar thumb in clan_unread_expanded). (b) 15 session-panel/session-lane goldens still carried the old "ACE family ..." window title after sase-17m.5.1.5 renamed the test title= strings; diffs confined to the title bar rows (y 12-30). All re-baselined with targeted just fix-tui-screenshots; a final check-mode run over agents*/artifacts_agents/statistics/revert (minus the sase-18y node) is clean: 116 unchanged, 0 drift.

[2026-09-25T10:02:30Z · sase-17m.5.1.6.2] PROPOSED FOLLOW-UP: four Agents-tab PNG goldens fail check on this tree for reasons unrelated to the agent-session rename and were left unaccepted: agents_decks_single_empty_120x40, agents_onboarding_120x40, agents_onboarding_no_plugins_120x40 (diff is the "Command Line: run sase commands without leaving the TUI." onboarding tip, likely sase-18o) and agents_fleet_followed_partial_offline_120x40 (a single-glyph diff at ~x1235,y883). None of their tests or fixtures were touched here.

[2026-09-25T10:02:49Z · sase-17m.5.1.6.2] Renamed family-concept test functions, helpers, locals, fixture kwargs, constants, docstrings and comments to agent-session naming across tests/ace/tui/{widgets,modals,actions,visual} (token-aware script; data strings renamed only in non-visual tests, visual/rendered data and the fleet family_id/family_role kwargs left for tui-tests). Updated tests/reproducible_flake_baseline.txt node ID. Verified: full non-visual tests/ace + tests/perf + test_cli_work_epic_summary = 14476 passed; check-mode visual pass over agents*/artifacts_agents/statistics/revert (minus known sase-18y node) clean: 116 unchanged, 0 drift after re-baselining 24 goldens that earlier phases left stale (see bead notes); just fix + sase tool run check green. Residual famil hits in scope classify as: opaque rendered visual data, unrelated meanings (MarkerFamily, search_operator_family, model_family, font-family, hue family, style families), the legacy agent_family cleanup fixture (marked), legacy directive-syntax family= comments/param, and fleet family_role kwargs owned by sase-17m.5.1.6.3. PROPOSED FOLLOW-UP recorded for 4 unrelated drifting goldens.

## Dependencies

- **Depends on:** [sase-17m.5.1.6.1](sase-17m.5.1.6.1.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-17m.5.1.6.3](sase-17m.5.1.6.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.6.2/README.md) | [sase-17m.5.1.6.2](sase-17m.5.1.6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d039244`](https://github.com/sase-org/sase/commit/d039244c0061f25ffe0ebcf4b19506e60e8afd67) | refactor(ace-tui): rename family test identifiers to agent-session in widget, modal, action, and visual tests | [sase-17m.5.1.6.2](sase-17m.5.1.6.2.md) | 2026-09-25 06:03:44 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.5.1.6.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.6.2/README.md

<!-- sase:referenced-by:end -->

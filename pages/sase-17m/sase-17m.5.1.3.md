# Bead: sase-17m.5.1.3 — Artifacts-pane contract, row kinds, and completion kinds

[Bead Pages](../README.md) / [sase-17m.5.1](sase-17m.5.1.md) / sase-17m.5.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.md) · **Assignee:** `sase-17m.5.1.3` · **Size:** medium
**Created:** 2026-09-25 00:06:04 EDT · **Closed:** 2026-09-25 02:30:51 EDT
**Plan:** [202609/agent\_session\_ace\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover.md)

## Description

contract-completion: rename the Agents-pane relation family/agent_family_container to session/agent_session_container, the grouping mode by_family (label Family, keys family) to by_session (label Session), and _artifact_tab_model FAMILY. Keep the Patch RelationKind.FAMILY. Rename the row kinds and identifiers in widgets/artifacts (agents_list, agents_navigation, agents_revival, query_rows) and relations/agents.py. Change the agent completion candidate kind "family" to "session" across the completion models, directive completion, and the prompt-bar completion rows. Update the artifacts contract goldens and the completion parity tests.

## Notes

[2026-09-25T06:30:16Z · sase-17m.5.1.3--1] PROPOSED FOLLOW-UP: 4 tribe tests fail on clean HEAD (roster kind label became session in sase-17m.5.1.1 but tests still expect build · family): tests/ace/tui/widgets/test_agent_display_tribe.py::test_tribe_levels_have_distinct_glance_triage_inspect_and_forensics_jobs and tests/ace/tui/widgets/test_agent_display_tribe_roster.py::test_expanded_panel_roster_has_fixed_gutter_and_one_target_row, test_collapsed_panel_omits_entry_heading_cursor_and_gutter, test_tribe_section_overrides_are_scoped_and_publish_anchors. Belongs with sase-17m.5.1.4 (tribe visible copy; Composition 1 family copy is still family): decide the roster kind copy and update the build · family expectations together.

[2026-09-25T06:30:28Z · sase-17m.5.1.3--1] PROPOSED FOLLOW-UP: just check fails on clean HEAD at lint (test waits): tests/ace/tui/command_line/test_policy_io.py:48 private _wait_for helper (from sase-17x.13.7); rename it to a domain-specific name or use sase.ace.testing.wait.wait_for. Clean HEAD also fails lint (symvision): unused CdResolution in command_line/builtins.py and PathCompletionRequest in command_line/sources.py, and validate: init memory --check wants sase/memory/README.md regenerated (sase init memory).

[2026-09-25T06:30:51Z · sase-17m.5.1.3--1] Agents-pane relation renamed to session/agent_session_container and grouping to by_session (label Session); Patch RelationKind.FAMILY and the Patch grouping keys kept as unrelated meanings. Agent completion kind is now session with glyph S (badge "session · N"); the core value_role "family" stays as a marked legacy reader mapped to kind session. Revival seed-query session term fixed: _parse_seed_query/_row_matches_terms previously ignored session: seeds (only accepted family), now accepts session and reads row.agent_session. Goldens re-baselined via just fix-tui-screenshots (scope targeted): 7 updated, 0 created/removed, pixel diff confined to the changed text regions (family->session labels, F->S glyph, session badge), each region viewed old-vs-new; no golden files renamed. Also updated test_link_follow_flat_panes reveal-context test (label "session big", renamed test_agent_session_shell_context). Check: sase tool run check stopped at lint (test waits) on tests/ace/tui/command_line/test_policy_io.py:48, a pre-existing failure on clean HEAD (fmt, ruff, mypy, flags, pyscripts passed before it). Ran the remaining stages individually: changelog, patch/stitch terminology, committed-plans pass; symvision and validate (memory README) fail identically on a clean HEAD worktree; test-scoped 8119 passed / 5 failed: 1 was mine (fixed), the other 4 tribe roster tests fail identically on clean HEAD (recorded as PROPOSED FOLLOW-UP for sase-17m.5.1.4). epic-symbols: none.

## Dependencies

- **Depends on:** [sase-17m.5.1.2](sase-17m.5.1.2.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-17m.5.1.4](sase-17m.5.1.4.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.5.1.3.md) | [sase-17m.5.1.3](sase-17m.5.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f7cbb59`](https://github.com/sase-org/sase/commit/f7cbb59f3588c0dc2c921c0c06c17d7595365eb1) | refactor(agent-session): rename Artifacts-pane contract, row kinds, and completion kinds (sase-17m.5.1.3) | [sase-17m.5.1.3](sase-17m.5.1.3.md) | 2026-09-25 02:32:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.5.1.3--1][1] | Need the phase scope to decide on pre-existing tribe test failures | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.5.1.3.md

<!-- sase:referenced-by:end -->

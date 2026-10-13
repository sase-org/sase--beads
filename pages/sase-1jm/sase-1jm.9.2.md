# Bead: sase-1jm.9.2 — Retired Artifacts strip, migration correctness, docs, and goldens

[Bead Pages](../README.md) / [sase-1jm.9](sase-1jm.9.md) / sase-1jm.9.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.land.md) · **Assignee:** `sase-1jm.9.2` · **Size:** medium
**Created:** 2026-10-12 14:50:51 EDT · **Closed:** 2026-10-12 20:09:47 EDT
**Plan:** [202610/agents\_archive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_completion.md)

## Description

retire-pane-finish: make the test and visual startup fixtures follow the production artifacts_agent_pane_retired state, fix the Help Guide digits, pane show -j, global show_artifacts_agents redirect, and the toast marker. Validate migrated saved queries against the archive profile, sweep the stale docs, and capture the renumbered-strip and toast goldens.

## Notes

[2026-10-13T00:06:49Z · sase-1jm.9.2] PROPOSED FOLLOW-UP: 10 check failures reproduce identically on clean base c4d84f9a1a (verified via git stash): test_project_display_presentation_audit path-label exemptions, test_new_project_source hidden counts, test_agent_archive_parking grouping-only, test_agent_jump_legend dismissed marker, test_agent_jump_panel_prefix revive cells, test_node_finder_modal x2 (rapid keystrokes, snapshot-rows GC), test_agent_display_workflow_async state reads, test_agent_display_meta_priority project-shown, and test_app_import_budget startup budget (already tracked by sase-1ic)

[2026-10-13T00:09:47Z · sase-1jm.9.2] retire-pane-finish done: fixtures follow production retired strip (fast/visual/descriptions/conformance both-states, agents goldens pinned flag-off); Guide digits + help Agent-Pane section follow resolver with tests; pane show agents -j emits JSON; show_artifacts_agents available every tab when retired; toast marker only when shown; migration validates via canonical_agents_tab_query (negated dismissed + unvalidatable stay behind, tribe:epic fixture); docs swept (configuration/ace/query_language/visual-grammar); 2 new goldens (retired strip, toast) + 331 regens inspected per-group, help goldens untouched for land-proof; check: lint/fmt/symvision/SASE-validation pass, 7 own regressions fixed (79 focused green), 10 base-identical failures recorded as follow-up

## Dependencies

- **Depends on:** [sase-1jm.9.1](sase-1jm.9.1.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.9.8](sase-1jm.9.8.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.2/README.md) | [sase-1jm.9.2](sase-1jm.9.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`95430b5`](https://github.com/sase-org/sase/commit/95430b58aa54c97bc97e1a95b3bde850577f04f1) | feat(ace): finish retired Artifacts Agent pane strip, migration, docs, and goldens | [sase-1jm.9.2](sase-1jm.9.2.md) | 2026-10-12 20:13:59 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.9.2][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.2/README.md

<!-- sase:referenced-by:end -->

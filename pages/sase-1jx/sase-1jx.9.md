# Bead: sase-1jx.9 — Wizard shell and the Source stage

[Bead Pages](../README.md) / [sase-1jx](README.md) / sase-1jx.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.49.linker.w1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.49.linker.w1.md) · **Assignee:** `sase-1jx.9` · **Size:** medium
**Created:** 2026-10-11 11:13:48 EDT · **Closed:** 2026-10-11 19:57:59 EDT
**Plan:** [202610/new\_project\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard.md)

## Description

tui-source: build the NewProjectModal shell (stepper, provider strip with health chips, stage machine) and the Source stage (paste-anything filter, streamed classified groups, hidden-count footer, resume rows, live detail card), pushed directly in tests only.

## Notes

[2026-10-11T23:57:50Z · sase-1jx.9--1] PROPOSED FOLLOW-UP: `sase tool run check` test-scoped has six failures reproduced identically on clean base 117f4cebbc (54,895 passed, 18 skipped): test_project_current_help_documents_resolution_and_json; test_every_value_slot_is_kinded_choiced_or_hinted (new missing project/suggest:owner); test_tracked_marker_path_passing_sites_are_reviewed (new unreviewed run_agent_wait_deps.py:_scoped_project_rows); test_project_shown_when_no_patch; test_tui_app_import_stays_under_startup_budget (3516 vs 3513); test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data. Existing tracking: sase-1k4 covers both Project: fake/tmp header failures; sase-1jm.2.1.5 already records the import-budget and marker-audit test nodes; sase-18s tracks the kind-coverage test node. No matching bead found for the current-project help assertion or the new project/suggest owner slot; epic land agent should triage those.

[2026-10-11T23:57:59Z · sase-1jx.9--1] Source stage complete: targeted modal tests passed (4); all five requested PNG cases updated/verified visually; just fmt completed. sase tool run check passed non-test gates but its six test-scoped failures reproduced on clean base 117f4cebbc (54,895 passed, 18 skipped) and are recorded in a PROPOSED FOLLOW-UP with existing bead citations. epic-symbols reported no leftovers.

## Dependencies

- **Blocks:** [sase-1jx.10](sase-1jx.10.md) ◐ · ⧖ 2026-10-11
- **Depends on:** [sase-1jx.6](sase-1jx.6.md) ✓ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.9.md) | [sase-1jx.9](sase-1jx.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4a5c040`](https://github.com/sase-org/sase/commit/4a5c04043b7b8711043a219c6585947e35274353) | feat(tui): add test-pushable New Project Source stage | [sase-1jx.9](sase-1jx.9.md) | 2026-10-11 20:02:18 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.9--1][1] | Confirm phase closure and recorded verification before final declaration | 5 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.9.md

<!-- sase:referenced-by:end -->

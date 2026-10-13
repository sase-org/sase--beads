# Bead: sase-1jx.13.6.4 — Finish Source stage teardown, layout, and spec states

[Bead Pages](../README.md) / [sase-1jx.13.6](sase-1jx.13.6.md) / sase-1jx.13.6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.13.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.13.land.md) · **Assignee:** `sase-1jx.13.6.4` · **Size:** medium
**Created:** 2026-10-12 19:35:36 EDT · **Closed:** 2026-10-12 22:52:30 EDT
**Plan:** [202610/new\_project\_wizard\_final\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard_final_repairs.md)

## Description

source-stage: stop cancelled owner refreshes from touching an unmounted modal, keep automatic provider fallback out of preferences, restore account sanitizing, show real cache age, collapse every detail card below 30 rows, make the no-owners card reachable, fix ref-less disabled rows, keep remedy refreshes, serialize preference writes, and tighten the Source tests.

## Notes

[2026-10-13T02:52:09Z · sase-1jx.13.6.4] PROPOSED FOLLOW-UP: just-check scoped lane has 8 failures that reproduce identically on the clean base tree (verified via stash): agent_archive_parking quitting-persists-grouping, agent_display_workflow_async snapshot-render, agent_jump_legend dismissed_marker, agent_jump_panel_prefix revive-cells, project_display_presentation_audit path-label-exemptions, agent_display_meta_priority project-shown-when-no-patch, node_finder rapid-keystrokes, app_import_budget 3517-vs-3513 modules; plus 1 KNOWN node_finder dismissed_modal (witness 0c18cf2d6c4cf95e93ad199602868cf6). None touch Source wizard files.

[2026-10-13T02:52:30Z · sase-1jx.13.6.4] All 11 source-stage items done and verified. Teardown: CancelledError propagates, teardown flag plus DOM-presence guard stop post-await touches (Textual prunes children before parent on_unmount), _loading always settles; tested with real blocked owner tasks. Fallback persists only user selections (select_provider persist=False). Chip sanitizes account, shows real fetched_at age, drops cached when live. Every card collapses below 30 rows with resize re-eval; no-owners card shows with Create row (github_orgs for gh only); ref-less disabled rows show enable copy; remedy refresh queues behind loads; hints use fit_hint_segments (epic-symbol row dropped); prefs writes locked with unique temp files plus concurrency test; weak tests tightened (fallback highlight, SuspendNotSupported, paste focus, Popen+hook perf guard). Focused suites 38 passed; visual goldens regenerated and --check clean twice incl TZ=UTC (new create_80x24, dropped 84x28); full check lints green, 8 scoped failures reproduce on clean base (recorded as follow-up). epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1jx.13.6.3](sase-1jx.13.6.3.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.13.6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.6.4/README.md) | [sase-1jx.13.6.4](sase-1jx.13.6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c69c312`](https://github.com/sase-org/sase/commit/c69c31236f7c773b6d2d7a51ef146739141623ce) | feat(new-project-wizard): finish Source stage teardown, layout, and spec states | [sase-1jx.13.6.4](sase-1jx.13.6.4.md) | 2026-10-12 22:54:31 EDT |

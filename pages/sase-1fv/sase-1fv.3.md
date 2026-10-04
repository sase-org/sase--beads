# Bead: sase-1fv.3 — Existing row and override mode in the save-location picker

[Bead Pages](../README.md) / [sase-1fv](README.md) / sase-1fv.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0w7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0w7.md) · **Assignee:** `sase-1fv.3` · **Size:** medium
**Created:** 2026-10-04 06:33:03 EDT · **Closed:** 2026-10-04 07:40:05 EDT
**Plan:** [202610/existing\_macro\_snippet\_editing.md](https://github.com/sase-org/sase--plans/blob/main/202610/existing_macro_snippet_editing.md)

## Description

picker-existing-row: teach the shared choice builders and picker modal to render an optional `e` Existing action row and an override mode. In override mode, rows are filtered by whether the name fits and badged with an injected after-save outcome. The live flows do not pass these options yet.

## Notes

[2026-10-04T11:18:48Z · sase-1fv.3] PROPOSED FOLLOW-UP: just _lint-symvision unused-public findings in src/sase/axe/runner_kill_provenance.py (KillProvenance, classify_runner_kill, format_kill_classification, oom_kill_evidence, reset_oom_baseline) reproduce on unmodified files identical to clean HEAD; already recorded on sase-1fu.3 note #1 and sase-1fs.1. No dedicated task bead. Does not block this phase.

[2026-10-04T11:39:14Z · sase-1fv.3] PROPOSED FOLLOW-UP: tests/tool/test_detach.py::test_watchdog_reports_ended_join_monitor failed the 14-worker scoped lane (ToolRun 365b549936c4d536882c8c730b49b981) with tool run store is busy: database is locked and passed isolation (6.00s); same SQLite busy class as sase-18t. Unrelated to picker Existing row.

[2026-10-04T11:39:19Z · sase-1fv.3] PROPOSED FOLLOW-UP: tests/ace/tui/test_launch_context_source.py::test_every_tick_rebroadcasts_to_mounted_views failed the 14-worker scoped lane (ToolRun 365b549936c4d536882c8c730b49b981) with LaunchContextState identity AssertionError and passed isolation (2.24s); already tracked by sase-1fn. Unrelated to picker Existing row.

[2026-10-04T11:40:05Z · sase-1fv.3] Existing row and override mode land in the shared choice builders and picker modal. macro_location_choices/snippet_location_choices take existing/override_name/shadowed_by; ExistingRowSpec and EXISTING_CHOICE_ID are public. Override omits e, disables namespace-rebasing rows, badges shadowed destinations, and defaults current→last used→first unshadowed selectable. Modal renders e with ✎, skips existing in empty/default fallback, and shows e existing in hints. Unit tests cover existing/switching/empty/override; PNG goldens existing_macro, existing_snippet, override captured. Live flows still omit these kwargs (sase-1fv.5/6). ExistingRowSpec is --epic-symbol keyed to sase-1fv.5. just check ToolRun 365b549936c4d536882c8c730b49b981: 52398 passed; 5 KNOWN unused runner_kill_provenance symbols (sase-1fu.3); NEW flakes sase-1fn and sase-18t passed isolation.

## Dependencies

- **Blocks:** [sase-1fv.5](sase-1fv.5.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1fv.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fv.3/README.md) | [sase-1fv.3](sase-1fv.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`763cc9f`](https://github.com/sase-org/sase/commit/763cc9fca334c8d2009789f368ef01aa9f40debe) | feat(tui): add Existing row and override mode to the save-location picker | [sase-1fv.3](sase-1fv.3.md) | 2026-10-04 07:41:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1fv.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fv.3/README.md

<!-- sase:referenced-by:end -->

# Bead: sase-1nn.6 — Run Full CI on the repaired tip and fix every other red

[Bead Pages](../README.md) / [sase-1nn](README.md) / sase-1nn.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.137](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.137.md) · **Assignee:** `sase-1nn.6` · **Size:** medium
**Created:** 2026-10-23 11:30:06 EDT · **Closed:** 2026-10-23 13:56:39 EDT
**Plan:** [202610/v0\_18\_1\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release.md)

## Description

full-ci: get a Full CI run on a tip containing the build-core fix, triage every non-visual red job plus any other Master Gate red, and fix what is deterministic.

## Notes

[2026-10-23T17:56:00Z · sase-1nn.6] PROPOSED FOLLOW-UP: test_compact_scroll_refits_after_resize still times out in CI after sase-1nn.4 — Full CI 39987573569 (3.12/3.13/3.14) and Master Gate 39987151505 (HEAD 1a3a7022d1, shard 8 only remaining red) wait_for timed out after 5.0s. Owned by modal-sizing (sase-1nn.4).

[2026-10-23T17:56:12Z · sase-1nn.6] PROPOSED FOLLOW-UP: Full CI visual-test is red on run 39987573569 (artifacts ace-visual-artifacts, visual-failure-report.html). Owned by visual-lane (sase-1nn.5).

[2026-10-23T17:56:17Z · sase-1nn.6] PROPOSED FOLLOW-UP: local just check on a core-identity-changed full-suite escalation still hits the same 4 KNOWN TUI failures recorded on sase-1nn.3/sase-1nn.4: test_tui_app_import_stays_under_startup_budget (sase-1ic), test_gc_policy::test_freeze_happens_once (witness 0565caed0d1ee997557a16ec01dc1ecb), test_census_off_by_default, test_populated_perf_renderable_covers_every_panel.

[2026-10-23T17:56:22Z · sase-1nn.6] PROPOSED FOLLOW-UP: tests/monitor/test_monitor_owner_cleanup.py::test_owner_cleanup_stops_monitor_child_and_suppresses_followup failed once under tests/monitor/ -n 8 (assert not is_process_running); no matching bead. Unrelated to this phase; did not reproduce on the diagnostics-file -n 8 runs.

[2026-10-23T17:56:39Z · sase-1nn.6] full-ci done. ci-workflows commit b2a4c380cf is on origin/master. Dispatched Full CI 39987573569 on 1a3a7022d1 (contains the build-core fix). build-core, lint, tutorial-tests, perf-floors, ace-page-group-isolation green. test 3.12/3.13/3.14 each failed the same 4 nodes: three fix_tui_screenshots CLI tests (PYTEST_ADDOPTS -p plugin name treated as a path selector; fixed in _has_restricting_args + isolated tests) and test_compact_scroll_refits_after_resize (owned by sase-1nn.4). visual-test red (owned by sase-1nn.5). Master Gate 39987151505 on HEAD: only shard 8 modal-sizing red. Also fixed test_supervisor_freezes_stage_manifest_and_retained_log_metadata first-range race seen on Master Gate 39977879162. Proof: 20/20 serial + 3x -n 8 on repaired files; sase tool run check 540426e8 succeeded. epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1nn.3](sase-1nn.3.md) ✓ · ⧖ 2026-10-23
- **Blocks:** [sase-1nn.7](sase-1nn.7.md) ✓ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.6/README.md) | [sase-1nn.6](sase-1nn.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bdec291`](https://github.com/sase-org/sase/commit/bdec291c77b0de1aab4c00abecef7430761db736) | fix(ci): treat PYTEST\_ADDOPTS -p values as plugins, not selectors | [sase-1nn.6](sase-1nn.6.md) | 2026-10-23 13:59:55 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.2a.cld][1] | E3 readiness: sase-1nn status | 1 |
| read-by | [agent:sase-1n6.5.1.5.2.1.2--1][2] | Need existing timeout evidence for proposed follow-up routing | 1 |
| read-by | [agent:sase-1nn.6][3] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.1.5.2.1.2.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.6/README.md

<!-- sase:referenced-by:end -->

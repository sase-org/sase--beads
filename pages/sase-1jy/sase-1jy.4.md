# Bead: sase-1jy.4 — Resolve scopable waiters from a scoped view in wait\_checks

[Bead Pages](../README.md) / [sase-1jy](README.md) / sase-1jy.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zo](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zo.md) · **Assignee:** `sase-1jy.4` · **Size:** medium
**Created:** 2026-10-11 11:18:33 EDT · **Closed:** 2026-10-11 17:26:14 EDT
**Plan:** [202610/wait\_checks\_scoped\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_checks_scoped_view.md)

## Description

scoped-wait-checks: build the resolving and confirmation views from scoped rows for scopable live waiters, build the full view lazily only for unscopable ones, and require a read-only host parity sweep over every waiting marker.

## Notes

[2026-10-11T20:56:25Z · sase-1jy.4] Host parity sweep (read-only, no publish, no-op sync_hint): 925 waiting.json markers (833 pending, 92 already-ready) on athena. Shapes: waiting_for_only=620, waiting_for+wait_for_beads=148, wait_for_beads_only=3, wait_for_epics_of+waiting_for=7, wait_for_fork_sources=6, @tribe=5, wait_for_artifacts=1, other=135. scopable=906 unscopable=19 parse_failures=0 mismatches=0 on resolve_wait_release/dependency_member_dirs/terminal_blockers. Live waiters=30 (all scopable). Snapshot load 17928 rows in 1962ms; full index 2241ms. Live-tick after load: full 2062ms vs scoped 238ms (134 vs 17928 view rows).

[2026-10-11T21:25:57Z · sase-1jy.4] PROPOSED FOLLOW-UP: just check NEW failures are not this phase — test_tui_app_import_stays_under_startup_budget 3516 vs 3513 (sase-1ic) and test_workflow_snapshot_render / test_project_shown_when_no_patch (Project tmp/fake vs sase/my_project) fail identically on the clean base tree; test_empty_panel_semicolon/escape (sase-1al), test_agy_warm_probe_skips_version_spawn, and test_agent_run_continues_past_all_known_stage failed in the suite and passed isolated on the clean tree.

[2026-10-11T21:26:14Z · sase-1jy.4] Scoped wait_checks views land: live markers read once; scopable waiters resolve and confirm from select_scope_rows (union keys + waiter dirs); unscopable waiters use a lazy full view. Counters scoped_waiters/full_view_waiters added; docs and default_config updated. Verified mixed scoped+full add_many sizes, confirmation defer on a newer failed run, bead-only scoped view, 120 wait_checks/scope tests, and a read-only host parity sweep of 925 markers with 0 mismatches (906 scopable). Live-tick after load: 2062ms full vs 238ms scoped (134 vs 17928 rows). just check NEW failures reproduced on the clean tree or flaked in isolation (see PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-1jy.1](sase-1jy.1.md) ✓ · ⧖ 2026-10-11
- **Depends on:** [sase-1jy.3](sase-1jy.3.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jy.6](sase-1jy.6.md) ✓ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jy.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jy.4/README.md) | [sase-1jy.4](sase-1jy.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`89572ca`](https://github.com/sase-org/sase/commit/89572caad6f9adb6097f1be7ced58ca35230b531) | feat(wait): resolve scopable waiters from a scoped wait\_checks view | [sase-1jy.4](sase-1jy.4.md) | 2026-10-11 17:28:01 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jy.4][1] | Need notes, remaining work, and epic DECISIONS for scoped-wait-checks | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jy.4/README.md

<!-- sase:referenced-by:end -->

# Bead: sase-1ou.1 — Make the flake-baseline gate reach a truthful verdict again (sase-1og)

[Bead Pages](../README.md) / [sase-1ou](README.md) / sase-1ou.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1oh.land--1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.land.md) · **Assignee:** `sase-1ou.1` · **Size:** medium
**Created:** 2026-10-27 09:20:59 EDT · **Closed:** 2026-10-27 10:23:46 EDT
**Plan:** [202610/backlog\_epic\_2\_top\_five\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/backlog_epic_2_top_five_task_beads.md)

## Description

flake-baseline: drop the duplicate fixed-at directive that makes tools/selection_health --fail-on-new-flake exit 2, add a regression test that parses the committed baseline, then reconcile the 64 exceedances the unmasked gate reports (fixed-at for verified fixes, baseline entries only under existing open beads, follow-ups for the rest), and close sase-1og.

## Notes

[2026-10-27T14:22:43Z · sase-1ou.1] PROPOSED FOLLOW-UP: import-budget recurrence — tests/ace/tui/test_app_import_budget.py fails deterministic on clean base (3541 modules vs 3539 cap; 146 gate-countable failures 09-28..10-27, fails focused too); closed sase-1ic tracked an earlier instance (3576 vs 3570, closed done 10-26); needs owner triage (defer imports or +1/reopen sase-1ic), left as gate exceedance

[2026-10-27T14:22:56Z · sase-1ou.1] PROPOSED FOLLOW-UP: stale TUI pilot load-flake cluster (all pass focused at base, last gate-countable failures early-Oct, no open bead) — panel_shell semicolon, screenshot_export tolerates_signal, launch_context_bar agents_row_fit (closed sase-1g2), artifacts_limit_keys ctrl_j (closed sase-1fy), prompt_next_word auto_space (closed sase-1ib), directive_completion x4 (matches_aliases, includes_representative, ctrl_t_alias, percent_partial), prompt_tab_focus_steal x5, launch_context_source every_tick, top_bar busy_cluster, agent_display_workflow_async, meta_priority project_shown, scoreboard conformance_warns, agy usage_probe; 19 nodes left as gate exceedances for land-agent triage

[2026-10-27T14:23:01Z · sase-1ou.1] PROPOSED FOLLOW-UP: doc-phrase audit flake cluster (pass focused, recent gate evidence) — test_agent_session_terminology (failures to 10-21) and test_sase_turn_terminology (to 10-23); no open bead and no attributable fix commit found; left as gate exceedances

[2026-10-27T14:23:16Z · sase-1ou.1] PROPOSED FOLLOW-UP: misc load-flake cluster (all pass focused at base, no open bead; closed-bead refs where they exist) — kind_coverage, agents_sync bounded_drain (11x 10-13..10-20), commit_publication_inline tagged_commit (10-21..10-24), new_project owner_switch (10-18), monitor_handler start_implicit (to 10-25), proc_producer inventory (to 10-24), isolation_guards x2 (to 10-21), agent_launch_executor preallocated (10-03), deferred_workspace_flow (10-17), plan_validate facade (closed sase-1k5; 10-11/10-17 failures postdate the corrects change 117f4cebbc, fix unidentified), plugin_latest enrich (closed sase-1jt; env-dependent spread 10-03..10-14), started_at home_mode marker (closed sase-1mf; burst 10-17 incl. trees containing f2a7b802f9, fix unidentified); 14 nodes left as gate exceedances

[2026-10-27T14:23:46Z · sase-1ou.1] Flake-baseline gate reaches a truthful verdict: duplicate fixed-at dropped (kept 2026-09-22 instant, both commits named), regression test added (20/20 pass, fails on pre-fix file), 64 exceedances reconciled to 41 (14 baselined under sase-18t/sase-13a/sase-1em/sase-137/sase-1nr/sase-1ny; 9 fixed-at with verified fixes; 49 dead directives + closed-bead entries pruned), gate exits 1 not 2, sase tool run check 58064 passed with only the 3 known clean-base reds. Owned task sase-1og closed done. Remaining 41 = 5 epic-owned (sase-1oj/sase-1om) + 36 in 4 follow-up notes; epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1ou.2](sase-1ou.2.md) ◐ · ⧖ 2026-10-27
- **Blocks:** [sase-1ou.3](sase-1ou.3.md) ◐ · ⧖ 2026-10-27
- **Blocks:** [sase-1ou.4](sase-1ou.4.md) ◐ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.1/README.md) | [sase-1ou.1](sase-1ou.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e608de2`](https://github.com/sase-org/sase/commit/e608de2db6c2406bf614d53f31c34c774dbd47c0) | fix(tests): repair flake-baseline gate verdict and baseline hygiene | [sase-1ou.1](sase-1ou.1.md) | 2026-10-27 10:25:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ou.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.1/README.md

<!-- sase:referenced-by:end -->

# Bead: sase-1bc.12 — Unflag, document, measure, and record memory

[Bead Pages](../README.md) / [sase-1bc](README.md) / sase-1bc.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0t4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0t4.md) · **Assignee:** `sase-1bc.12` · **Size:** medium
**Created:** 2026-09-27 10:57:17 EDT · **Closed:** 2026-09-28 18:27:12 EDT
**Plan:** [202609/agents\_dynamic\_tabs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_dynamic_tabs.md)

## Description

finish: delete the agent_tabs flag's Off branches and close its bead; finish the docs; add the tab-switch bench; do the full golden pass; add the agent-tab and machine-tab glossary strands and update the node-panel strand.

## Notes

[2026-09-28T20:46:50Z · sase-1bc.12] PROPOSED FOLLOW-UP: opt-in project-default tabs (ace.agent_tabs.default: main | project)

[2026-09-28T20:47:02Z · sase-1bc.12] PROPOSED FOLLOW-UP: bead-remembered tabs for epics launched later from the Artifacts pane

[2026-09-28T20:47:13Z · sase-1bc.12] PROPOSED FOLLOW-UP: app-level O keybinding for the layout ladder if users ask for it

[2026-09-28T20:47:25Z · sase-1bc.12] PROPOSED FOLLOW-UP: confirm tab-switch 50ms / j/k 16ms contract targets on a dev host; sandbox bench (tests/ace/tui/bench_tui_jk_agent_tabs.py) measures switch key-to-paint p50 ~200ms p95 ~775ms and j/k p95 ~25ms at 500 roots, with _descriptors_for_strip per-switch recompute as the top sync hotspot

[2026-09-28T21:32:32Z · sase-1bc.12--1] PROPOSED FOLLOW-UP: visual goldens left partial — 16 nodes fail identically on clean base (sandbox visual env); rerun just fix-tui-screenshots on a dev host to apply agents_tab_strip_empty/feed_unavailable/query_hides, axe_chop_run_info, usage_attention_narrow/badges_crowded_narrow, 7 tool_runs nodes, output_variables_multi_agent

[2026-09-28T22:26:52Z · sase-1bc.12--2] PROPOSED FOLLOW-UP: 6 just-check failures reproduce identically on clean base HEAD 995e057116 (verified via worktree): test_agents_help_renders_sorted_subcommands, test_default_config_matches_public_schema (tool_runs run_tool/stop_run), test_every_value_slot_is_kinded_choiced_or_hinted, test_current_source_avoids_agent_family_identifiers (cli_tab agent_family), test_tui_app_import_stays_under_startup_budget (3458 vs 3450), test_inventory_matches_live_production_source (stale tool_runs_pane entry); plus KNOWN stale Justfile --epic-symbol entries for closed bead sase-1bt

[2026-09-28T22:27:12Z · sase-1bc.12--2] agent_tabs unflag complete: flag module deleted, Off branches removed across 38 src files, docs/schema/memory strands updated, bench added (switch key-to-paint p50 ~200ms p95 ~775ms at 500 roots; j/k p95 ~25ms per tab), goldens applied via just fix-tui-screenshots. Fixed 42 unflag-fallout test failures (g-prefix launch-tab hints, tribe-modal cancel semantics, default-scoped selection memory, scoped jump anchors, ladder refresh count, latched-tab empty state); all 205 tests in 18 affected files pass, ruff clean. 6 failures + stale sase-1bt epic-symbols reproduce identically on clean base, recorded as follow-up.

## Dependencies

- **Depends on:** [sase-1bc.10](sase-1bc.10.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bc.11](sase-1bc.11.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bc.8](sase-1bc.8.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bc.9](sase-1bc.9.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.12.md) | [sase-1bc.12](sase-1bc.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f379c64`](https://github.com/sase-org/sase/commit/f379c6417954120ee24f1b21160894c9d6d91835) | feat(agents-tabs): unflag agent tabs and update fallout tests (sase-1bc.12) | [sase-1bc.12](sase-1bc.12.md) | 2026-09-28 18:29:29 EDT |

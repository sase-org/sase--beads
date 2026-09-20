# Bead: sase-11y.8 — Migrate background commands to oneshot service procs

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m3.md) · **Assignee:** `sase-11y.8` · **Size:** medium
**Created:** 2026-09-16 14:42:05 EDT · **Closed:** 2026-09-20 13:02:33 EDT
**Plan:** [202609/service\_host\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_1.md)

## Description

oneshots: move the ! background-command flow onto the durable proc store as transient oneshot service procs with recorded exit codes and durable rerun, render them as a distinct oneshot section on the Services tab, and keep legacy slot dirs readable behind a sunset flag.

## Notes

[2026-09-20T17:00:26Z · sase-11y.8] PROPOSED FOLLOW-UP: just check symvision is red on master with 25 unused public symbols this phase did not touch — src/sase/sdd/_store_clone_admission.py, _store_clone_remote.py, src/sase/ace/tui/models/_agent_runner_slot_capacity.py, src/sase/completion/runtime_cache_generation.py, src/sase/service/host_support.py (gateway_builtin_argv, sase_command), src/sase/service/host_reporting.py (observation, write_host_status); the two service ones may just need an --epic-symbol re-key for the gateway-telegram phase.

[2026-09-20T17:00:54Z · sase-11y.8] PROPOSED FOLLOW-UP: tests failing on an unchanged tree: tests/test_capacity_gate_to_admission.py (2, queue_weight is None), tests/ace/tui/test_lazy_tier2_reconcile_apply.py::test_changed_query_incomplete_load_after_reconcile_rearms, tests/completion/test_candidates_project_providers.py::test_bead_candidates_without_a_store_returns_empty_list (reads this workspace real bead store), and visual test_agents_collapsed_panel_png_snapshot / test_queued_clan_counts_png_snapshot (No nodes match #agent-list-panel).

[2026-09-20T17:01:21Z · sase-11y.8] PROPOSED FOLLOW-UP: the sase-11y.7 Services tab retint (tab label now teal) never regenerated its PNG goldens, so every axe_*.png had drifted; this phase regenerated all 17 axe goldens together with its own oneshot-row changes. The bgcmd-slot:<n> concurrency key is fenced per project by the store (not globally), so oneshot_display_rows re-homes a cross-project duplicate; a store-level global key namespace would let that code go.

[2026-09-20T17:01:47Z · sase-11y.8] PROPOSED FOLLOW-UP: sase service proc run picks a #n index from the proc store only and does not skip legacy ~/.sase/axe/bgcmd slot dirs (the TUI does); harmless until a legacy dir and a new row collide (the durable row wins the index) and disappears when the bgcmd_legacy_slots flag bead sase-13w is removed in the sunset phase.

[2026-09-20T17:02:33Z · sase-11y.8] ! background commands and sase service proc run now share procs.oneshot.submit_oneshot: a detached transient oneshot service proc (service={mode:oneshot,source:transient}) with recorded exit code, store-owned log, kill via durable proc kill, durable rerun, and #1-#9 indices via bgcmd-slot:<n> keys (only running oneshots consume an index; finished history never blocks a launch). Services tab renders a '── oneshots ──' section with ▷/✓/✗ glyphs, muted palette and exit-code/age chips; dashboard badge names the exit code. Legacy ~/.sase/axe/bgcmd slot dirs stay readable behind new sunset flag bgcmd_legacy_slots (bead sase-13w), never written. Verified: real-supervisor tests (exit code 3 recorded, output, running-slot fencing), collector smoke against real rows, ruff/mypy/flags/fmt gates green, scoped lane green except 3 failures that also fail on an unchanged tree, 17 axe PNG goldens regenerated and inspected. Not green: just check symvision has 25 pre-existing unused-symbol findings in files this phase did not touch (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-11y.10](sase-11y.10.md) ◐ · ⧖ 2026-09-16
- **Depends on:** [sase-11y.4](sase-11y.4.md) ✓ · ⧖ 2026-09-16
- **Depends on:** [sase-11y.7](sase-11y.7.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.8/README.md) | [sase-11y.8](sase-11y.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9316a24`](https://github.com/sase-org/sase/commit/9316a24e5b05016e0819c9f3a5e687a84f878d99) | feat(service): run ! background commands as transient oneshot service procs | [sase-11y.8](sase-11y.8.md) | 2026-09-20 13:36:06 EDT |

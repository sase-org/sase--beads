# Bead: sase-11y.7 — Services tab in the TUI

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m3.md) · **Assignee:** `sase-11y.7` · **Size:** large
**Created:** 2026-09-16 14:42:04 EDT · **Closed:** 2026-09-20 10:29:33 EDT
**Plan:** [202609/service\_host\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_1.md)

## Description

services-tab: rename the AXE tab display label to Services, render service-proc nodes with routine/job nodes nested under the Scheduler node, add start/stop/enable/disable keys and the host status line, replace the footer pill, and wire gear exclusion plus the configurable -service Procs default query.

## Notes

[2026-09-19T12:24:18Z · sase-11l.11.5.land--1] DISCOVERED ISSUE: test_x_does_not_toggle_the_host_on_nested_scheduler_rows fails isolated on 423316a051 (x on nested Scheduler rows calls _start_service_host). Contract added in 485a6082e1. Recorded on epic sase-11y with file:explicit:e6751fe4134815e6e564a922; declined a new task because this phase owns Services-tab key routing.

[2026-09-19T14:20:50Z · sase-11l.11.5.land.f0--code] The Services-tab `x` vs `!x` routing issue from LANDING BLOCKED / DISCOVERED ISSUE is fixed (plan:202609/landing_gate_test_failures_1.md). Bare `x` toggles a selected service proc and is a no-op on nested Scheduler rows, empty selection, and host chrome. `!x` on the Services tab always starts/stops the host. Tests in `tests/ace/tui/actions/test_service_host_keys.py` cover empty selection, nested rows, and `!x` with a proc selected. Leave this phase/epic open; remaining Services-tab work is unchanged.

[2026-09-20T10:54:24Z · sase-11y.7] PROPOSED FOLLOW-UP: sase-11y platform/config service facades have no non-test consumer — at sunset, privatize or delete CapturedServiceEnvironment, read_service_environment, NativeInspection, NativeServiceDefinition, ServicePlatformApplyResult, build_native_definition, inspect_native_service, readiness_warnings, service_platform_supported, ServiceFieldProvenance, compose_service_config, resolve_service_enablement, clear_service_enablement instead of carrying epic-symbol entries.

[2026-09-20T14:29:33Z · 0o0] Gate repair verified 2026-09-20 in sase_32 at master 6087c0a8e plus the 5-file working-tree fix (it lands with this agent's host-owned commit).

Fixed (the two defects sase-11y.7 actually caused):
1. Symvision: is_gear_eligible_row (ace/tui/_proc_observer_models.py) and service_enablement_chip (ace/tui/widgets/bgcmd_list.py), both introduced by 92dd554c4, are now private; test_services_phase_closure.py imports the private name.
2. TUI import budget: two eager import edges added by this phase (axe_display/_data.py from c2befdbb3, widgets/bgcmd_list.py from 92dd554c4) pulled sase.service.{status,boot,config,paths,state,control} into TUI startup. Both are deferred (TYPE_CHECKING plus function-local imports; duck-typed enablement check). Importing sase.ace.tui.app now loads 3286 modules (was 3292; cap 3290 unchanged) and the only sase.service.* modules are sase.service and sase.service.restart. test_app_import_budget.py now also asserts sase.service.status and sase.service.control are absent, so a future eager edge fails with a named module.

Per-gate results:
- just fmt and just _lint-ruff: clean.
- just _lint-symvision: exactly the 26 unrelated symbols (sdd/_store_clone_*, ace/tui/models/_agent_runner_slot_capacity.py, service/host_support.py, service/host_reporting.py, completion/runtime_cache_generation.py); neither of ours remains.
- just _lint-mypy: exactly the same 20 no-untyped-def errors in main/ace_tmux.py, ace_tmux_session.py, ace_tmux_window.py; none new.
- test_app_import_budget.py, test_services_phase_closure.py, actions/test_axe_stop_quit.py: 37 passed.
- pytest tests/ace tests/service -n 8: 12 failed, 12881 passed. The 12 are the pre-existing ones (10 in test_agents_zoom_panel_files.py, test_commit_view_modal_toggles_plan_and_restores_cached_diff, test_changed_query_incomplete_load_after_reconcile_rearms); the import-budget failure is gone and nothing new appeared.
- just check: still red, and only at lint (mypy) with the same 20 errors. Those come from the e89aa2566 tmux split (not this phase; no sase-11y.7 commit touches those files) and were tracked by sase-13k, which was closed upstream by 45df42549 while this ran; that fix is not yet in this checkout.

Unrelated red gates: mypy sase-13k (+1); symvision 26 symbols sase-13s (+1, notes that our 2 are fixed here); lazy-tier2 failure sase-13n (+1; owned by epic sase-13i.3); import-budget beads sase-13p and sase-13r (noted with root cause and fix, close on evidence once this lands); 11 path-truncation tests new sase-13u; test_real_fakey_* PNG pair new sase-13v; collapsed-panel and queued-clan PNG tests attributed to sase-13i.2 (45a7895b6) and recorded as a DISCOVERED ISSUE note on epic sase-13i. tests/perf/bench_tui_trace.py p95 is a slow-marked xprompt-tokenizer bench in no agent-run lane; out of scope. just check-full was not run. Parent epic sase-11y and open siblings sase-11y.8 and sase-11y.10 untouched.

The 13 --epic-symbol "sase-11y(...)" entries in the Justfile are unchanged; they stay keyed to the open parent epic, and note 3 on this bead already records their sunset follow-up. No new follow-up is proposed here.

## Dependencies

- **Blocks:** [sase-11y.10](sase-11y.10.md) ✓ · ⧖ 2026-09-16
- **Depends on:** [sase-11y.2](sase-11y.2.md) ✓ · ⧖ 2026-09-16
- **Depends on:** [sase-11y.4](sase-11y.4.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.8](sase-11y.8.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.7.md) | [sase-11y.7](sase-11y.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c2befdb`](https://github.com/sase-org/sase/commit/c2befdbb3e83e6531c61d28af5dacb91f661ce16) | feat(tui): add services tab controls | [sase-11y.7](sase-11y.7.md) | 2026-09-18 06:59:19 EDT |
| sase | [`92dd554`](https://github.com/sase-org/sase/commit/92dd554c4cc33db81ae9232a31d1a31d5cc2f493) | feat(tui): finish Services tab host chrome, health pill, and quit flow | [sase-11y.7](sase-11y.7.md) | 2026-09-20 07:32:38 EDT |

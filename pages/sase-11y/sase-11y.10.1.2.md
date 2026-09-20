# Bead: sase-11y.10.1.2 — Remove the service\_host beta flag and its Off branches

[Bead Pages](../README.md) / [sase-11y.10.1](sase-11y.10.1.md) / sase-11y.10.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.md) · **Assignee:** `sase-11y.10.1.2` · **Size:** large
**Created:** 2026-09-20 13:56:13 EDT
**Plan:** [202609/service\_host\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset.md)

## Description

flag-removal: delete the `service_host` registry entry and every gate that reads it, delete the Off branches in the scheduler handler, the TUI, the mobile gateway, doctor, init, and the service control plane, make the On branch unconditional, and close flag bead sase-12m.

## Notes

[2026-09-20T19:57:52Z · sase-11y.10.1.2] PROPOSED FOLLOW-UP: run `sase update` (or fast-forward the dev editable checkout) on athena and apollo BEFORE deploying this change. sase-telegram fix f99521c ("stop consulting the service_host flag in the rearm check") is on origin/master, but the local editable install is still at f05f53b (v0.4.19); without it _service_host_owns_receiver() hits a raising FeatureFlag lookup inside a bare except, returns False, and ensure_receiver_running() re-arms a second getUpdates consumer.

[2026-09-20T19:58:22Z · sase-11y.10.1.2] PROPOSED FOLLOW-UP: AxeCollectedData.axe_status / axe_metrics are permanently None after this phase (the only producer was the deleted legacy proc.get_axe_status/read_metrics path). Retire those collector fields and the update_empty_axe_display status / full_cycles parameters they feed.

[2026-09-20T19:58:48Z · sase-11y.10.1.2] PROPOSED FOLLOW-UP: docs/ (ace.md, architecture.md, axe.md, cli.md, getting_started.md, init.md, mobile_gateway.md) still documents the removed service_host flag and the scheduler restart --verify-timeout / stop --force options until the docs phase (sase-11y.10.1.5) lands.

[2026-09-20T19:59:28Z · sase-11y.10.1.2] PROPOSED FOLLOW-UP: KeybindingFooter.set_service_health(None) (the "restore legacy AXE pill" path in widgets/_keybinding_status.py) has no production caller now that _push_service_health always pushes derived health; only tests/ace/tui/test_services_phase_closure.py exercises None. Retire the None/legacy-pill branch.

[2026-09-20T20:00:06Z · sase-11y.10.1.2] PROPOSED FOLLOW-UP (pre-existing on HEAD 8ae9ac1ea, verified by stashing this change and rerunning; not caused by this phase): (1) `just _lint-symvision` fails: 26 unused-public findings (e.g. sdd/_store_clone_*.py, ace/tui/models/_agent_runner_slot_capacity.py, service/host_support.py, service/host_reporting.py) and a stale --epic-symbol sase-14d.4(play_sound_file) for the now-closed bead sase-14d.4, so `sase tool run check` stops at that stage. (2) 7 tests fail on HEAD: tests/test_capacity_gate_to_admission.py x2 (queue_weight None), tests/ace/tui/test_lazy_tier2_reconcile_apply.py::test_changed_query_incomplete_load_after_reconcile_rearms, tests/ace/tui/test_epic_panel_arrival_frames.py x4. (3) golden agents_selected_panel_clan_collapse_120x40.png already drifts on HEAD; left un-accepted here. (4) agents_fleet_production_families_120x40.png drifted only in the full parallel visual run and is clean alone on this tree (load flake).

[2026-09-20T20:01:09Z · sase-11y.10.1.2] CLOSE NOTE. (1) telegram-rearm fix f99521c is on sase-telegram origin/master, but the local dev editable install is still at f05f53b (v0.4.19), so `sase update` (or a fast-forward of that checkout) is required on athena and apollo before this change is deployed there; see the PROPOSED FOLLOW-UP note. (2) Verified an unregistered SASE_FEATURE_FLAGS key is a warning, not an error: `SASE_FEATURE_FLAGS='{"service_host": true}' sase flag list` and `... sase service status` both exit 0 (flag list prints "warning: unknown feature flag 'service_host' ignored"); resolver.py emits FeatureFlagDiagnostic(severity=warning, code=unknown_key) and tests/feature_flags/test_resolver.py::test_env_beats_overrides_and_unknown_env_key_warns_only now also pins severity == "warning". A stale "service_host": true in ~/.sase/feature_flags.json only warns and is cleaned by ACE deferred cleanup. (3) Flag bead sase-12m was closed with the removal; `just _lint-flags` passes; `sase bead epic-symbols sase-11y.10.1.2` reports none. (4) `just fix-tui-screenshots`: ran check-only first (24 updated, 0 created, 0 stale), inspected every group, then applied a TARGETED update of 22 axe-family goldens (axe_*, help_guide_axe, link_rail_axe_twelve_links) whose diffs were exactly (a) the always-on service-host clause "Services · host ○ stopped · press !x to start" leading the AXE info-panel header row (truncating the chop label at 60-70 col widths), (b) footer label "start axe" -> "start service host" (wrapping the footer by a row at narrow widths), and (c) the footer pill "SVC STOPPED" -> "SVC 0/0" (derive_service_health(None) is healthy 0/0 when no snapshot). Not accepted: agents_selected_panel_clan_collapse_120x40 (already drifts on unmodified HEAD) and agents_fleet_production_families_120x40 (clean alone; only drifted under full parallel load). (5) Verification: `sase tool run check` passes every stage except symvision, which fails identically on unmodified HEAD (stale --epic-symbol sase-14d.4(play_sound_file) plus 26 pre-existing unused-public findings; this change adds none); the stages it then skipped (toobig, validate, validate-committed-plans) pass when run directly; `just test-scoped` ran ~44k tests with 9 failures: 1 mine (test_axe_info_panel_loading_clears, fixed), 1 load flake (test_stage_timeline, passes alone), 7 pre-existing on HEAD (listed in the follow-up note).

## Dependencies

- **Depends on:** [sase-11y.10.1.1](sase-11y.10.1.1.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.3](sase-11y.10.1.3.md) ◐ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.4](sase-11y.10.1.4.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.2.md) | [sase-11y.10.1.2](sase-11y.10.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ef99009`](https://github.com/sase-org/sase/commit/ef990099089ba524972140bd4268631e11c74b29) | refactor(service): remove the service\_host beta flag and its Off branches | [sase-11y.10.1.2](sase-11y.10.1.2.md) | 2026-09-20 17:08:43 EDT |

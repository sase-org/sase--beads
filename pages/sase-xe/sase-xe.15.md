# Bead: sase-xe.15 — Fleet-wide acceptance, flag removal, and polish

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.15

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.15` · **Size:** medium
**Created:** 2026-09-06 14:06:49 EDT · **Closed:** 2026-09-07 17:20:40 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

acceptance: run the performance and failure acceptance matrix (local-first paint, j/k p95 under hung hosts, laziness tiers, fault recovery), finish keyboard-only/narrow/no-color UX review with updated PNG snapshots, remove the remote_dispatch beta flag by making the On branch unconditional, and record proposed follow-ups.

## Notes

[2026-09-07T16:32:56Z · 03p.f1] PROPOSED FOLLOW-UP: zero-machine discovery affordance - the 'Connect a machine' action is unreachable before enrollment, so the hidden Focus/Fleet strip has no in-TUI escape hatch.

Surfaced by the user during flag-toggle testing (see the DISCOVERED ISSUE note on sase-xe for the full trace). Fits this phase's keyboard-only/narrow/no-color UX review and polish scope.

The gap: app.connect_agent_machine is titled 'Agents: show remote machine status' and its availability predicate is ctx.selected_agent_remote (src/sase/ace/tui/commands/_availability_agents.py:117-118). That requires an enrolled machine and a selected remote row, so the action never appears in the state the plan wrote it for. Plan line 305 specifies the strip is hidden until enrollment 'and a Connect a machine command-menu action opens setup guidance'; line 890 lists it under fleet-ui scope. The hiding half shipped, the guidance half did not.

Suggested shape: make a setup-guidance command available when zero machines are configured (pointing at 'sase machine add' / 'sase machine discover'), keeping the existing selected-remote status action as a separate, differently-titled command.

Second observation from the same session, no code change implied but worth an acceptance-matrix line: an in-place ACE hot-restart cannot pick up a flag toggle. install_process_feature_flags (src/sase/feature_flags/snapshot.py:173) writes SASE_FEATURE_FLAGS into the process environ at startup, os.execvp carries it forward, and the env layer outranks the state layer the TUI pane writes - so the toggle appears to do nothing until a fresh 'sase ace' is launched from a shell without that variable. The pane's 'shadowed' marker (feature_flags_pane_rendering.py:74) only renders when saved and env disagree, so it stayed silent here. Relevant to this phase only until the flag is removed, but the underlying restart-vs-env behavior outlives it.

[2026-09-07T19:04:25Z · sase-xe.15] PROPOSED FOLLOW-UP: acceptance-matrix perf/snapshot coverage is still unbuilt for Fleet/Focus — build it, then run it.

No j/k p95 benchmark scenario exists for the hung-host / reconnect-storm / event-burst cases the plan's performance contract calls for. tests/ace/tui/bench_tui_jk_agents.py only covers synthetic local-agent fixtures (_install_agents_fixture / _install_clan_agents_fixture in tests/ace/tui/_bench_tui_jk_helpers.py); neither takes a fleet/remote/hung-host parameter, and docs/perf_runbook.md has no Fleet-specific capture recipe.

No PNG snapshot exists for any Fleet/Focus/Follow state at all (tests/ace/tui/visual/ has zero fleet/dispatch/follow-star coverage). The fleet-ui phase spec named these states explicitly: followed row, partial counts, offline host, empty/loading/unavailable/zero-result Fleet.

Both require either a fake federation-worker/gateway fixture or a way to synthesize resolved remote rows offline; scope that fixture as part of the follow-up rather than building it ad hoc.

[2026-09-07T19:04:55Z · sase-xe.15] PROPOSED FOLLOW-UP: four of nine failure-table scenarios have no fault test.

Checked every scenario in the plan's Failure behavior table against tests/dispatch/, tests/test_dispatch_*.py, and tests/doctor/test_checks_dispatch.py:
- Missing/disabled provider: src/sase/doctor/checks_dispatch.py builds "provider not installed"/"provider disabled" messages and src/sase/dispatch/machine_service.py raises MachineRegistryError for a disabled provider, but no test exercises either branch.
- Host hangs / laptop sleeps: no timeout/hang fault-injection test anywhere under tests/dispatch/ or tests/test_dispatch_federation.py (which only covers supervisor spawn, IPC frame decode, and oversized-response rejection).
- Unauthorized/incompatible host: src/sase/dispatch/fleet_client.py builds a FleetGatewayError from any non-2xx status, but no test drives a 401/403 response.
- Name/PID reuse (exact-instance fencing): no fleet-specific test found; tests/test_agent_loader_dedup_pid_reuse.py is local-agent dedup, not remote-row fencing.

Also: launch reply lost is covered for mutations (tests/test_dispatch_mutations.py::test_lost_reply_reconciles_under_the_same_key) and attention (tests/test_dispatch_attention.py::test_remote_attention_lost_reply_reconciles_under_the_same_key) but not for %dispatch launch itself — tests/test_dispatch_launch.py has no lost-reply/reconciliation test, unlike its two siblings.

[2026-09-07T19:05:23Z · sase-xe.15] PROPOSED FOLLOW-UP: hidden-Fleet laziness has no TUI-level regression test.

The mechanism is real: src/sase/ace/tui/actions/agents/_fleet.py _run_agents_fleet_refresh only fetches the catalog `if self.current_agents_subtab == "fleet" or source == "manual"`, and gates summary/followed_batch/attention/catalog calls behind `if config.enabled:` (FederationConfig.enabled requires both a running worker and configured hosts). But no test exercises _run_agents_fleet_refresh directly to assert a hidden Fleet subtab does zero catalog hydration — grep for _run_agents_fleet_refresh / _schedule_agents_fleet_refresh / current_agents_subtab under tests/ returns nothing outside the source files. Existing coverage (tests/test_dispatch_federation.py::test_empty_remote_hosts_keep_facade_disabled_without_rust_binding, tests/dispatch/test_machine_service.py::test_list_machines_is_offline) only proves the config/service layer stays inert with zero machines, not that the TUI refresh path skips hydration when Fleet is merely unselected.

[2026-09-07T19:06:16Z · sase-xe.15] PROPOSED FOLLOW-UP: sase_dispatch is a real pluggy hook group but was never wired into the plugin inventory.

src/sase/dispatch/providers.py defines DISPATCH_ENTRY_POINT_GROUP = "sase_dispatch" with a real hookspec (dispatch_provider_specs, dispatch_discover) intended for third-party dispatch-provider plugins, matching the dispatch-plugins phase spec ("New entry-point group sase_dispatch added to ENTRY_POINT_GROUPS ... SASE_DISABLE_PLUGIN_DISPATCH comes free from the group-name convention"). But src/sase/plugins/inventory.py ENTRY_POINT_GROUPS never lists "sase_dispatch", so `sase plugin list`/doctor plugin-inventory diagnostics never surface dispatch providers, and SASE_DISABLE_PLUGIN_DISPATCH does not work. The two built-in providers (builtin@https, builtin@tailnet) are also not registered as real pyproject.toml entry points — grep for "builtin@" in pyproject.toml finds nothing; they are hard-coded in _BuiltinDispatchProviders instead, unlike every other builtin@-style provider in this codebase.

[2026-09-07T19:07:34Z · sase-xe.15] PROPOSED FOLLOW-UP: docs/plugins.md entry-point-group count is stale, and now doubly so.

docs/plugins.md:15 says "Sase defines nine entry point groups" with a 9-row table (sase_artifact_refs, sase_file_hooks, sase_task_types, sase_vcs, sase_workspace, sase_llm, sase_xprompts, sase_config, sase_plugin_manifest). src/sase/plugins/inventory.py ENTRY_POINT_GROUPS actually has 10 entries — sase_finalizers is missing from the doc table (pre-existing staleness, not caused by this epic). If the sase_dispatch registration gap above gets fixed, the doc will need an 11th row too. Confirmed still unfixed at close of this phase.

[2026-09-07T19:08:04Z · sase-xe.15] PROPOSED FOLLOW-UP: add a reference memory note documenting remote dispatch operations.

This epic deliberately left sase/memory/ untouched throughout (per its own phase instructions), so there is no reference memory covering: sase machine enrollment/repair flow, dispatch: config shape, the follow-store/Focus-Fleet count semantics, or operational recovery for a quarantined/unreachable host. Someone landing routine dispatch work will have to re-derive this from source each time.

[2026-09-07T19:08:34Z · sase-xe.15] PROPOSED FOLLOW-UP: standard deferred items from the epic plan, recorded here per the acceptance phase closing instructions (not new discoveries — restating the plan's own out-of-scope list so the land agent triages them into task beads): an SSH tunnel dispatch provider; "fork here" (cross-host context migration, vs. the shipped fork-on-target); always-on notification delivery while ACE is closed; remote terminal/editor/tmux integration for remote agents; and any benchmark-driven tuning of the reconciliation cadence (jittered 30-60s summaries, exponential backoff) deferred pending real usage data.

## Dependencies

- **Depends on:** [sase-xe.14](sase-xe.14.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.15](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.15.md) | [sase-xe.15](sase-xe.15.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ac1ba1b`](https://github.com/sase-org/sase/commit/ac1ba1be92a6d3f082d4082436617c43443f692e) | feat: Fleet-wide acceptance, flag removal, and polish (sase-xe.15) | [sase-xe.15](sase-xe.15.md) | 2026-09-07 17:17:28 EDT |

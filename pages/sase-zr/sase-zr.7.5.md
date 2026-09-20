# Bead: sase-zr.7.5 — Corrected docs, targeted latency evidence, and combined verification

[Bead Pages](../README.md) / [sase-zr.7](sase-zr.7.md) / sase-zr.7.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.07](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.07.md) · **Assignee:** `sase-zr.7.5` · **Size:** medium
**Created:** 2026-09-16 14:25:15 EDT · **Closed:** 2026-09-20 09:33:30 EDT
**Plan:** [202609/sase\_zr\_close\_out.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_zr_close_out.md)

## Description

verify-close: correct the notification and Telegram inbound docs, record targeted before/after TUI gate-response latency evidence on an isolated fixture, run every changed repo's checks plus sase's combined check-full through sase_monitor, remove any epic scaffolding, and hand the narrowed-contract re-verification of parent sase-zr to the land agent.

## Notes

[2026-09-20T13:32:32Z · sase-zr.7.5] PROPOSED FOLLOW-UP: pre-existing check-full failures on clean tree — mypy no-untyped-def in src/sase/main/ace_tmux*.py, symvision private-misuse in ace_tmux_support.py/memory/selector_models.py, sase-telegram tests/test_receiver.py 15 failures; `just test-cost` hung >2h in this workspace

[2026-09-20T13:33:30Z · sase-zr.7.5] Docs corrected: notifications.md (approved vs committed semantics, failure outcomes and recovery, legacy bundles, table placement verified), sase-telegram inbound.md/README (stop procedure, upgrade caveat, auth note); prettier clean. Verification: fmt/keep-sorted/ruff/flags/pyscripts/test-waits/changelog/terminology/toobig/validate/committed-plans pass; mypy, symvision and telegram test_receiver failures are pre-existing (docs-only diff, reproduced on clean tree for telegram); test-cost timed out after 2h so full check-full did not complete. NOT DONE: fresh before/after latency p50/p95 evidence was not captured (only 2026-09-14 numbers in docs); no epic scaffolding existed. Land agent should re-verify sase-zr.

[2026-09-20T16:22:57Z · sase-zr.7.land] LATENCY EVIDENCE CAPTURED by the sase-zr.7 land agent on 2026-09-20, completing this phase's 'NOT DONE' item (note #2). Throwaway probe only -- the committed reusable probe stays descoped per the plan -- run on isolated fixtures with no real gates, then deleted.

METHOD. Path A: a synthetic ~/.sase/projects tree (3 projects x 500 artifact dirs = 1500, built with tests/perf/bench_agent_scan._build_synthetic_root, workflow_fraction 0.25) under a temp SASE_HOME. Classified both pulse paths through actions/event_refresh/_artifact_paths, then timed 25 matched pairs of the two loaders those routes call: load_agents_from_disk_with_state (the broad tier1 load the old project-level pulse forced) vs load_agent_artifact_delta_from_disk_with_state on the one answered dir (the exact route the new agent-dir pulse takes). Artifact index warmed first so neither route paid a one-time rebuild. Path B: 10 settlements through tests/gate_shell/_settlement_followup_helpers with a 150 ms follow-up-launch barrier, timing the real touch_shell_refresh_pulse call and the launcher return in the same run; 'before' is the launcher return because the old ordering published the pulse only after launch_or_record_followup returned.

PATH A -- acceptance receipt to Agents row data. Classification: the old project-level pulse is artifact_path_is_project_refresh_pulse=True with exact_dir=None (no row named); the new agent-dir pulse is project_pulse=False and resolves exact_dir to the answered agent's directory. Timings: before (broad tier1 load) p50 74.843 ms, p95 123.367 ms, max 185.587 ms; after (exact artifact-dir delta) p50 1.698 ms, p95 2.527 ms, max 2.537 ms; n=25 each. 44.1x cheaper at the median.

PATH B -- response publication to refresh-pulse visibility. Before (pulse after follow-up launch) p50 407.539 ms, p95 450.791 ms; after (pulse before follow-up launch) p50 97.684 ms, p95 130.297 ms; n=10 each. 309.9 ms earlier at the median, and no longer bounded by follow-up launch cost at all.

Both numbers are now also in docs/notifications.md, closing sase-zr landing-audit gap 11's 'no before/after latency numbers'.

J/K BENCHMARK NOT CONFIRMED. The plan also asked ace-fast-refresh to confirm the j/k p95 16 ms benchmark. pytest -s -m slow tests/ace/tui/bench_tui_jk.py failed 8 of 10 scenarios here, but the host was at load average 19.75 on 16 CPUs with a concurrent rustc/cc1 build, so these wall-clock key-to-paint numbers carry no signal -- open bead sase-lx documents exactly this confound for the same benchmark and explicitly says to re-measure on a quiet host first. The deterministic, load-independent guards that cover the same contract do pass: 76 tests across tests/perf/test_agents_display_rebuild_guard.py, tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py, tests/ace/tui/test_axe_status_read_cache.py and tests/test_notification_toast_polling_agent_refresh.py, including the quiet-tick no-reload guard.

## Dependencies

- **Depends on:** [sase-zr.7.3](sase-zr.7.3.md) ✓ · ⧖ 2026-09-16
- **Depends on:** [sase-zr.7.4](sase-zr.7.4.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.7.5/README.md) | [sase-zr.7.5](sase-zr.7.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`96b9133`](https://github.com/sase-org/sase/commit/96b91333326f4cbf644286625f6c439710e1bed5) | docs(notifications): correct fast decision acceptance, failure recovery and status semantics | [sase-zr.7.5](sase-zr.7.5.md) | 2026-09-20 09:35:12 EDT |
| sase-telegram | [`sase-telegram@4d20559`](https://github.com/sase-org/sase-telegram/commit/4d20559691a408d5c1908b59c7344daaca65be38) | docs(inbound): document real receiver stop procedure, upgrade caveat and chat authentication | [sase-zr.7.5](sase-zr.7.5.md) | 2026-09-20 09:37:59 EDT |

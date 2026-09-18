# Bead: sase-132.1 — Controlled baselines and startup observability gaps

[Bead Pages](../README.md) / [sase-132](README.md) / sase-132.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0n7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0n7.md) · **Assignee:** `sase-132.1` · **Size:** medium
**Created:** 2026-09-18 15:22:33 EDT · **Closed:** 2026-09-18 16:29:02 EDT
**Plan:** [202609/tui\_startup\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_startup_regression.md)

## Description

baseline: capture controlled quiet-host and busy-host loader benches plus traced live startups at a recorded deployed SHA, and close the instrumentation gaps this diagnosis hit - sub-stage spans inside agents.load_from_disk, spans for the axe surface first load (none exist in live traces today), a pre-mount split of process_start_to_on_mount, and a startup-window marker on spans so startup contention is directly queryable.

## Notes

[2026-09-18T20:26:43Z · sase-132.1] Captures at workspace SHA 0320daed701f (sase-core 8d5341a4d5e9 / 0.34.53) on athena, host_state=busy (loadavg ~17-37, 37-38 run_agent_runner.py). Index: ~/.sase/perf/sase-132.1_capture_index.json. Busy loader bench: ~/.sase/perf/sase-132.1_agent_load_tiering_busy-20260918T195252Z.json (archive 11851 artifacts, production_bounded p50 1759.6 ms / p95 1942.0 ms, source_scan p50 12038.6 ms). Importtime: ~/.sase/perf/sase-132.1_importtime-20260918T194901Z.txt (3286 import-time lines). Live traced startups: ~/.sase/perf/sase-132.1_live_busy-20260918T194913Z/ (3 runs, visible_ready 7.18/7.85/11.11 s) and profiled run ~/.sase/perf/sase-132.1_live_busy-20260918T195200Z/ plus ~/.sase/perf/sase-132.1_profile_busy-20260918T195200Z.txt. Recipe: tests/perf/capture_tui_startup.py documented in docs/perf_runbook.md.

[2026-09-18T20:27:08Z · sase-132.1] Instrumentation verified on live traces: agents.load_from_disk substages (dismissed_snapshot / provider / index / decode / projections), axe.startup + axe.load_status + axe.collect span with file_opens (legacy axe.collect event kept), startup_window=true until visible-ready stopwatch end, tui_startup.jsonl additive fields interpreter_cli_import_seconds / app_module_import_seconds / app_construct_seconds / compose_seconds without changing process_start_to_on_mount_seconds. Profiled run substages: dismissed_snapshot 4982 ms, index 761 ms, decode 203 ms, provider 1211 ms, projections 141 ms, outer load_from_disk 6335 ms; axe.collect 2879 ms file_opens=453.

[2026-09-18T20:27:34Z · sase-132.1] PROPOSED FOLLOW-UP: Quiet-host real-archive loader bench — athena stayed busy (load 17-37, 37+ run_agent_runner.py) so only host_state=busy JSON exists; recapture bench_agent_load_tiering.py --sase-home ~/.sase when load1<4 and zero agent runners, store as sase-132.1_agent_load_tiering_quiet-*.json.

[2026-09-18T20:28:00Z · sase-132.1] PROPOSED FOLLOW-UP: Defer or cache dismissed_bundle_identities_snapshot on the startup load_from_disk path — first-load query_summary_identities took 4982 ms of a 6335 ms startup agents.load_from_disk (span agents.load_from_disk.dismissed_snapshot); belongs to startup-sequence or loader-diet, not a telemetry gap anymore.

[2026-09-18T20:28:26Z · sase-132.1] PROPOSED FOLLOW-UP: tui_perf.md rule 14 still documents axe.collect as events; collector now also emits an axe.collect duration span with file_opens. Memory update is not a baseline-phase step; land agent can file a memory task if the rule should mention spans.

[2026-09-18T20:29:02Z · sase-132.1] Verified: live traces at SHA 0320daed701f emit agents.load_from_disk substages (dismissed_snapshot/provider/index/decode/projections), axe.startup/load_status/collect spans with file_opens, startup_window=true until visible-ready, and additive pre-mount fields on tui_startup.jsonl without changing process_start_to_on_mount_seconds. Busy-host bench production_bounded p50 1759.6 ms (11851 artifacts); 3 traced startups + pyinstrument profile + 3286-line importtime stored under ~/.sase/perf/sase-132.1_*. Quiet-host bench unavailable (athena load 17-37); proposed follow-ups noted. Tests: 84 passed (startup telemetry/observability/trace/axe collector/loader wiring/ace_handler). Recipe: tests/perf/capture_tui_startup.py / docs/perf_runbook.md. epic-symbols: none leftover.

## Dependencies

- **Blocks:** [sase-132.2](sase-132.2.md) ◐ · ⧖ 2026-09-18
- **Blocks:** [sase-132.3](sase-132.3.md) ◐ · ⧖ 2026-09-18
- **Blocks:** [sase-132.5](sase-132.5.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-132.6](sase-132.6.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-132.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-132.1/README.md) | [sase-132.1](sase-132.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8319c22`](https://github.com/sase-org/sase/commit/8319c2240817397540352638ba160c0cead93626) | feat(tui): add startup substages, axe spans, and pre-mount telemetry split | [sase-132.1](sase-132.1.md) | 2026-09-18 16:31:06 EDT |

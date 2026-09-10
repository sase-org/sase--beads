# Bead: sase-xe.16.11.7.13 — Live Athena-to-Apollo acceptance of the unified experience

[Bead Pages](../README.md) / [sase-xe.16.11.7](sase-xe.16.11.7.md) / sase-xe.16.11.7.13

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0hv](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0hv.md) · **Assignee:** `sase-xe.16.11.7.13` · **Size:** medium
**Created:** 2026-09-09 15:49:38 EDT
**Plan:** [202609/unified\_agents\_across\_machines.md](https://github.com/sase-org/sase--plans/blob/main/202609/unified_agents_across_machines.md)

## Description

live-acceptance: execute the research validation scenarios live between Athena and Apollo, record pane evidence, and capture the close evidence for the reopened parent phases.

## Notes

[2026-09-10T17:28:46Z · sase-xe.16.11.7.13] LIVE ACCEPTANCE FAILURE 2026-09-10T17:28Z: Athena and Apollo both installed SASE 0.17.1+366.g4f6eb2b17 / core 0.33.0+4.gdc3d0a8b4; dispatch doctor OK; machine init/discover/status OK for apollo; dirty source checkout guard refused before dispatch; #gh:sase dispatches reached Apollo and produced output. Blocker: authenticated fleet catalog/ACE did not surface the current live dispatch row, showed stale killed dispatch state instead, and advertised no lifecycle.stop, so ACE and `sase machine agent stop` could not perform exact-instance remote stop. Test agents were cleaned up target-locally with `sase agent kill -n`; phase intentionally left open.

[2026-09-10T17:28:49Z · sase-xe.16.11.7.13] PROPOSED FOLLOW-UP: Restore exact remote stop for newly dispatched agents - bare `sase machine agent stop -j apollo <dispatch-id>` could not find a live row because its name-filtered catalog lookup returned zero rows; ACE also filtered to zero for `machine:apollo <dispatch-id>`.

[2026-09-10T17:28:52Z · sase-xe.16.11.7.13] PROPOSED FOLLOW-UP: Repair remote fleet catalog freshness for gateway-launched agents - Apollo `sase agent list -j --all` showed live dispatch-2d20796b62f94e9168cf92b10d37a288, but Athena federation catalog returned stale dispatch-d3774de79e74a005e9cc527778128abd and omitted the current row even after `sase agent index rebuild`.

[2026-09-10T17:29:32Z · sase-xe.16.11.7.13] PROPOSED FOLLOW-UP: Persist Apollo gateway bridge configuration - live gateway initially answered hello but dispatch failed with `bridge_unavailable: agent_bridge` until the user service ExecStart included `--agent-bridge-command /home/bryan/.local/share/uv/tools/sase/bin/sase`; capture this in managed config/runbook to avoid regression.

[2026-09-10T17:30:01Z · sase-xe.16.11.7.13] PROPOSED FOLLOW-UP: Make gateway restart resilience explicit for launched children - restarting Apollo `sase-gateway.service` kept hello healthy but caused the then-running dispatch-e371346bab260d54d0a065ab1dfba5d9 observer to terminate early at 28s despite a requested 600s sleep; assess process group/session detachment or document expected behavior.

[2026-09-10T17:30:33Z · sase-xe.16.11.7.13] PROPOSED FOLLOW-UP: Clarify or preflight `%dispatch` plus explicit `%id` - Apollo rejected a launch with `launch_failed: agent_bridge:launch-text:name-cannot-be-provided-when-prompt-already-has-a-id-directive`; successful dispatches omitted `%id` and let the dispatch operation id become the remote name.

[2026-09-10T17:31:04Z · sase-xe.16.11.7.13] PROPOSED FOLLOW-UP: Inspect ACE target-picker focus after custom launch from a filtered remote view - while the prompt bar appeared active after choosing `#gh:sase`, Enter submitted a bulk `sase machine agent stop apollo ...` over the filtered Apollo rows instead of the typed launch; it failed safely because those rows lacked `lifecycle.stop`.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.12](sase-xe.16.11.7.12.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.13/README.md) | [sase-xe.16.11.7.13](sase-xe.16.11.7.13.md) | 0 |

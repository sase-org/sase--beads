# Bead: sase-kp.1 — Monitor marker fields on the agent scan wire

[Bead Pages](../README.md) / [sase-kp](README.md) / sase-kp.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yy/README.md) · **Assignee:** `sase-kp.1` · **Size:** small
**Created:** 2026-08-12 17:28:17 EDT · **Closed:** 2026-08-12 18:06:11 EDT
**Plan:** [202608/sase\_monitor.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_monitor.md)

## Description

core-wire: add the monitor marker fields to the Rust `AgentMetaWire` / `DoneMarkerWire` and their Python mirrors so monitor members survive the agent artifact scan.

## Notes

[2026-08-12T22:06:11Z · sase-kp.1] Added monitor_* fields to Rust AgentMetaWire/DoneMarkerWire (crates/sase_core/src/agent_scan/wire.rs), bumped AGENT_SCAN_WIRE_SCHEMA_VERSION 4->5, wired only_monitors filter into AgentArtifactIndexQueryWire + record_matches_selection, and added round-trip/old-record/only_monitors tests (all green via ./scripts/check.sh all in sase-core, commit cb91149). Mirrored the same fields on the Python side (agent_scan_wire_markers.py, agent_scan_wire_records.py, agent_scan_wire_conversion.py), added round-trip + pre-monitor-record tests in tests/test_core_agent_scan_wire.py, and bumped the tools/validate_sase_core_rs schema probe 4->5. Verified with just install && just check (all lint gates + scoped tests green) in the sase workspace, commit 3c37f8e36.

## Dependencies

- **Blocks:** [sase-kp.3](sase-kp.3.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kp.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.1/README.md) | [sase-kp.1](sase-kp.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3c37f8e`](https://github.com/sase-org/sase/commit/3c37f8e3651bae1f0b53b759efdafffa86a5e2fd) | feat(agent-scan): mirror monitor marker fields on the Python wire | [sase-kp.1](sase-kp.1.md) | 2026-08-12 18:03:25 EDT |

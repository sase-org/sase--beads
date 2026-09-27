# Bead: sase-1ab.10.3 — Land the sase-core contract flip

[Bead Pages](../README.md) / [sase-1ab.10](sase-1ab.10.md) / sase-1ab.10.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ab.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.land.md) · **Assignee:** `sase-1ab.10.3` · **Size:** medium
**Created:** 2026-09-27 08:44:30 EDT
**Plan:** [202609/sase\_turn\_rename\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename_finish.md)

## Description

core-flip: re-apply the orphaned contract-flip diff onto current sase-core master, give the gate_turn_id column migration artifact-index schema 35, prove current sase master against it, and land the feat! commit on sase-core origin/master.

## Notes

[2026-09-27T14:21:23Z · sase-1ab.10.3] Mirror constants pin-bump (sase-1ab.10.4) must move after the flip lands: src/sase/core/agent_scan_wire_records.py AGENT_SCAN_WIRE_SCHEMA_VERSION 10->11 and AGENT_ARTIFACT_INDEX_SCHEMA_VERSION 34->35 (extend SUPPORTED_* frozensets to include 11 and 35); src/sase/procs/models/common.py PROC_WIRE_SCHEMA_VERSION 3->4 (SUPPORTED set already includes 4); src/sase/dispatch/models.py FLEET_PROTOCOL_VERSION 2->3; src/sase/core/agent_launch_wire_records.py LAUNCH_PLAN_WIRE_SCHEMA_VERSION 2->3. No Python mirrors exist for RUNNER_CAPACITY_POLICY (6->7), AGENT_HOLD_WIRE (2->3), PROC_DISPATCH_WIRE (1->2), or FLEET_CONTRACT_SCHEMA (6->7); those are core-internal with dynamic probes. Flip commit not yet landed; sase-against-new-core proof still pending (extension build exceeded turn budget, handed to monitor).

[2026-09-27T14:22:20Z · sase-1ab.10.3] PROPOSED FOLLOW-UP: sase-core finalizer run_view prose still says shell-concept wording (wire.rs:36,105,120 doc comments: "Which kind of shell produced a run", "every member shell run", "one concrete shell finalizer run"; precedence.rs:192 "the shell sealed a plan"). No serialized shell-named fields there; classification/reword belongs to the acceptance sweep, not the contract flip.

[2026-09-27T14:22:34Z · sase-1ab.10.3] PROPOSED FOLLOW-UP: gateway test fleet_launch_replays_delayed_launch_and_reconciles_visible_row failed once under full sase-core check with Timeout("snapshot_refresh") then passed alone and on full re-run; matches known flake bead sase-15g, not the flip. No action.

## Dependencies

- **Depends on:** [sase-1ab.10.1](sase-1ab.10.1.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1ab.10.2](sase-1ab.10.2.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1ab.10.4](sase-1ab.10.4.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.10.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.10.3.md) | [sase-1ab.10.3](sase-1ab.10.3.md) | 0 |

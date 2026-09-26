# Bead: sase-1ab.1.1.3 — Fleet, runner capacity, and gateway

[Bead Pages](../README.md) / [sase-1ab.1.1](sase-1ab.1.1.md) / sase-1ab.1.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ab.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.1.md) · **Assignee:** `sase-1ab.1.1.3` · **Size:** medium
**Created:** 2026-09-26 00:28:17 EDT · **Closed:** 2026-09-26 01:46:30 EDT
**Plan:** [202609/sase\_core\_turn\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_turn_expand.md)

## Description

fleet-runtime: rename fleet row kinds, locator ids, owner status, and runner-slot shell fields, emit the legacy spellings, accept the new ones, and leave the fleet golden unchanged.

## Notes

[2026-09-26T05:46:06Z · sase-1ab.1.1.3] Remaining shell hits in fleet-runtime files: unrelated meaning = agent_runtime family_shell JSON fixtures (legacy input) and gate_shell_id column refs in agent_scan (scan-wires owns); legacy spelling pinned for contract-flip = agent_shell/historical_shell emits (status.rs), shell_id key + shell instance-key segment + shell- fallback prefix (locators.rs, fleet_catalog.rs, gateway resolution.rs), shell_start/stop_status keys (fleet_owner_facts.rs), agent_session_shell_kind/id/state keys (runner_capacity/wire.rs), validate_identifier("shell_id"); legacy binding name = none added in this phase.

[2026-09-26T05:46:16Z · sase-1ab.1.1.3] PROPOSED FOLLOW-UP: contract-flip must flip fleet-runtime legacy emits (agent_shell->agent_turn, historical_shell->historical_turn, shell_id->turn_id, shell segment->turn, shell- fallback->turn-, shell_start/stop_status, runner-slot keys) and bump FLEET_CONTRACT_SCHEMA_VERSION/FLEET_PROTOCOL_VERSION + RUNNER_CAPACITY_POLICY_SCHEMA_VERSION.

[2026-09-26T05:46:30Z · sase-1ab.1.1.3] fleet-runtime rename landed in sase-core: turn vocabulary with legacy emits + dual-input tests; verified just fast, fleet + runner_capacity + gateway committed_ suites green, and sase tool run check succeeded (e7939a7b); fleet_api_v1.json and schema versions unchanged

## Dependencies

- **Depends on:** [sase-1ab.1.1.2](sase-1ab.1.1.2.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ab.1.1.4](sase-1ab.1.1.4.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.1.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.1.1.3/README.md) | [sase-1ab.1.1.3](sase-1ab.1.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@20deb1b`](https://github.com/sase-org/sase-core/commit/20deb1b0c5b19f0f9ad3b6e34f765093dbb585da) | refactor(core): rename fleet runtime shell wires to turn vocabulary | [sase-1ab.1.1.3](sase-1ab.1.1.3.md) | 2026-09-26 01:47:36 EDT |

# Bead: sase-1ab.1.1.1 — Agent-scan wires and gate lookup

[Bead Pages](../README.md) / [sase-1ab.1.1](sase-1ab.1.1.md) / sase-1ab.1.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ab.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.1.md) · **Assignee:** `sase-1ab.1.1.1` · **Size:** medium
**Created:** 2026-09-26 00:28:14 EDT · **Closed:** 2026-09-26 00:49:26 EDT
**Plan:** [202609/sase\_core\_turn\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_turn_expand.md)

## Description

scan-wires: rename the agent-scan shell wires, hand-read meta keys, and gate-id lookup, pin legacy serde output, keep the SQLite column, and register the new gate lookup binding beside the legacy one.

## Notes

[2026-09-26T04:48:47Z · sase-1ab.1.1.1] Remaining concept hits in owned files: legacy serde spellings pinned for contract-flip (agent_session_shell/family_shell member keys, shell_kind key + proc value, GATE_TURN_INDEX_COLUMN="gate_shell_id" + idx name in storage/query/maintenance); legacy binding find_gate_shell_by_gate_id wrapper in sase_core_py/src/agent_scan/mod.rs; legacy-input JSON fixtures + legacy-emission assertions in wire/scanner/lineage tests; no unrelated-shell hits in owned files (triage gate_shell path fixture untouched per shared rule 7).

[2026-09-26T04:48:57Z · sase-1ab.1.1.1] PROPOSED FOLLOW-UP: contract-flip must flip agent_session_shell->agent_session_turn, family_shell removal, shell_kind->turn_kind + proc->monitor value, gate_shell_id column/index, and remove find_gate_shell_by_gate_id wrapper (wire.rs, scanner.rs, index/{storage,query,maintenance}, sase_core_py agent_scan/mod.rs).

[2026-09-26T04:49:07Z · sase-1ab.1.1.1] PROPOSED FOLLOW-UP: fleet-runtime phase owns agent_session_shell() fn, concrete_agent_session_shell_kind, record_is_concrete_agent_session_shell, ConcreteAgentSessionShellKind, kind_from_agent_session_shell, apply_shell_facts, runner_capacity agent_session_shell_kind/_id/_state wires, and gate-turn prose left in fleet_agent_session.rs.

[2026-09-26T04:49:26Z · sase-1ab.1.1.1] scan-wires done: AgentSessionTurn(Member/Gate) wires with legacy serde emission, turn_kind with monitor->proc mapping, 3-key/2-key hand-read helpers, gate_turn index lookup + GATE_TURN_INDEX_COLUMN pin, dual py bindings; verified: just fast ok, targeted suites green (agent_scan 156, runtime 34, fleet 144, runner 90, parity 10, py 9 incl. 5 new tests), sase tool run check succeeded (run ca7eb122, 142s); no schema/version/golden changes; no epic-symbols left

## Dependencies

- **Blocks:** [sase-1ab.1.1.2](sase-1ab.1.1.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.1.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.1.1.1/README.md) | [sase-1ab.1.1.1](sase-1ab.1.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c2c2f94`](https://github.com/sase-org/sase-core/commit/c2c2f94f54e71d3b009a776a213b044ad7bf18aa) | refactor(agent\_scan): rename session shell wires to session turn wires | [sase-1ab.1.1.1](sase-1ab.1.1.1.md) | 2026-09-26 00:50:45 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ab.1.1.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.1.1.1/README.md

<!-- sase:referenced-by:end -->

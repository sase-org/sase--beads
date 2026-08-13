# Bead: sase-ku.1 — Monitor supervision fields on the agent scan wire

[Bead Pages](../README.md) / [sase-ku](README.md) / sase-ku.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.1` · **Size:** small
**Created:** 2026-08-13 09:02:27 EDT · **Closed:** 2026-08-13 09:29:10 EDT
**Plan:** [202608/monitor\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_hardening.md)

## Description

wire: add the process-identity, settlement, idle-timeout, and follow-up-output marker fields to the Rust `AgentMetaWire` and its Python mirrors so the hardening phases have somewhere durable to record them.

## Notes

[2026-08-13T13:28:34Z · sase-ku.1] PROPOSED FOLLOW-UP: tests/main/test_project_handler_list_show.py::test_project_handler_imports_in_fresh_interpreter fails to collect standalone with a circular import (sase.project_aliases <-> sase.memory.read_log) when run in isolation; reproduces on clean master (pre-existing, unrelated to this phase).

[2026-08-13T13:29:10Z · sase-ku.1] Added monitor_pgid, monitor_supervisor_identity, monitor_settled, monitor_idle_timeout_seconds, monitor_next_output, monitor_request_fingerprint to Rust AgentMetaWire (wire.rs) and mirrored in Python agent_scan_wire_markers.py; bumped AGENT_SCAN_WIRE_SCHEMA_VERSION 5->6 in wire.rs and agent_scan_wire_records.py, updated tools/validate_sase_core_rs and its pinned-version test. Verified: cargo test --lib agent_scan:: (53 passed) and python_wire_parity integration test (8 passed) in sase-core; pytest tests/test_core_agent_scan_wire.py (15 passed, including fixed test_schema_version_pinned) and tools/validate_sase_core_rs (clean) after rebuilding sase_core_rs via just install; ruff+mypy clean on touched files. just check's scoped test lane showed 4 failures, all confirmed pre-existing/unrelated: 2 monitor tests flaky under parallel load (pass in isolation), 1 hypothesis-missing venv staleness (fixed by just install), 1 circular-import collection failure reproduced identically on clean master. just check's patch/stitch terminology lint gate also fails identically on clean master (pre-existing, unrelated).

## Dependencies

- **Blocks:** [sase-ku.3](sase-ku.3.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.6](sase-ku.6.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.7](sase-ku.7.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.1/README.md) | [sase-ku.1](sase-ku.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@87e4a4f`](https://github.com/sase-org/sase-core/commit/87e4a4f455192dd1f930925e2d46a67caacd25c0) | feat(agent-scan): add monitor supervision fields to the agent scan wire | [sase-ku.1](sase-ku.1.md) | 2026-08-13 09:30:37 EDT |
| sase | [`dc9da55`](https://github.com/sase-org/sase/commit/dc9da557631a7ecb8e16dc5ebefd24cc1f0fda4c) | feat(agent-scan): mirror monitor supervision fields on the Python wire | [sase-ku.1](sase-ku.1.md) | 2026-08-13 09:31:37 EDT |

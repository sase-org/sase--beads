# Bead: sase-ko.1 — Rust agent\_runners guard provider

[Bead Pages](../README.md) / [sase-ko](README.md) / sase-ko.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yx/README.md) · **Assignee:** `sase-ko.1` · **Size:** medium
**Created:** 2026-08-12 16:00:00 EDT · **Closed:** 2026-08-12 16:11:29 EDT
**Plan:** [202608/chop\_agent\_runners\_guard.md](https://github.com/sase-org/sase--plans/blob/main/202608/chop_agent_runners_guard.md)

## Description

core-guard: add the `agent_runners` guard variant, the `holds_runner_slot` agent snapshot field, the decision and validation logic, and config-authority acceptance in `../sase-core`.

## Notes

[2026-08-12T20:11:29Z · sase-ko.1] Added the agent_runners guard variant to sase-core: wire.rs (ChopGuardConfigWire::AgentRunners{max}, ChopAgentSnapshotWire.holds_runner_slot), decision.rs (skip when active+holds_runner_slot count exceeds max, naming an offending agent; earlier guards still short-circuit first), config.rs (agent_runners allowed in validate_guard_provider with max validated via existing validate_nonnegative_integer, both keyed/tagged spellings, unknown_guard_provider message updated). Added decision + config-validation tests in axe_chop/tests.rs and a python-binding round-trip test in sase_core_py/src/lib.rs. Verified with 'just check' from the sase-core repo root (full workspace build, clippy, fmt, and test suite, including the sase_core_py binding tests) - all green. Committed and pushed to sase-core master as a0a6ca4.

## Dependencies

- **Blocks:** [sase-ko.2](sase-ko.2.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ko.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ko.1/README.md) | [sase-ko.1](sase-ko.1.md) | 0 |

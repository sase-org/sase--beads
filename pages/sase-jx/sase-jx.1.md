# Bead: sase-jx.1 — Overrun classifier in the Rust core

[Bead Pages](../README.md) / [sase-jx](README.md) / sase-jx.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ye](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ye/README.md) · **Assignee:** `sase-jx.1` · **Size:** medium
**Created:** 2026-08-12 09:06:00 EDT · **Closed:** 2026-08-12 10:09:55 EDT
**Plan:** [202608/axe\_chop\_overrun\_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/axe_chop_overrun_indicator.md)

## Description

core_classifier: add the host-I/O-free `axe_overrun` module, its versioned wire records, and the `classify_chop_overrun` PyO3 binding that turns one chop's cached run history plus its lumberjack interval into a level/ratio verdict.

## Notes

[2026-08-12T14:09:55Z · sase-jx.1] Added crates/sase_core/src/axe_overrun/ (wire.rs, classify.rs, tests.rs) in sase-org/sase-core, registered pub mod axe_overrun in lib.rs alphabetically between axe_chop/axe_status. classify_chop_overrun implements the 4-step rule from the design: blocking_ms derivation (script_duration_ms priority > running-elapsed > action_* unknown > duration_ms), status-based sampling filter (excludes skipped/missing_script/check_error, drops unknown statuses and action_* without script_duration_ms), over-at->=interval, and over/intermittent/none leveling off the newest-vs-older sampled runs. Added PyO3 binding chop_overrun_wire_schema_version()/classify_chop_overrun() in crates/sase_core_py/src/lib.rs next to the axe_status pair, with binding-inventory doc entries and round-trip tests. Verified with 'just check' from the sase-core root (fmt + clippy -D warnings + full workspace test suite incl. sase_core_py binding tests) — all green, 16 new classify unit tests + 2 new binding tests passing. Changes left uncommitted in the sase-core checkout at sase/repos/external/gh/sase-org/sase-core since the dependent snapshot_wiring phase builds directly from this working tree.

## Dependencies

- **Blocks:** [sase-jx.3](sase-jx.3.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jx.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jx.1/README.md) | [sase-jx.1](sase-jx.1.md) | 0 |

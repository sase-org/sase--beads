# Bead: sase-mg.1 — Add an indexed output-variable query contract to sase-core

[Bead Pages](../README.md) / [sase-mg](README.md) / sase-mg.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02u.md) · **Assignee:** `sase-mg.1` · **Size:** medium
**Created:** 2026-08-15 15:36:41 EDT · **Closed:** 2026-08-15 15:55:29 EDT
**Plan:** [202608/powerful\_variables.md](https://github.com/sase-org/sase--plans/blob/main/202608/powerful_variables.md)

## Description

core-variable-index: project stored output variables into the agent artifact index and expose typed, deterministic history queries through Rust and PyO3.

## Notes

[2026-08-15T19:55:29Z · sase-mg.1] Implemented sase-core schema v21 output-variable projection, grouped history wires, PyO3 query binding, and lifecycle tests; verified cargo fmt, targeted core/PyO3 output-variable tests, and sase-core just check.

[2026-08-15T19:57:52Z · sase-mg.1] Verified cargo fmt; cargo test -p sase_core output_variable -- --nocapture; cargo test -p sase_core_py agent_output_variable_history_binding_round_trips_python_dict -- --nocapture; just check in linked sase-core

## Dependencies

- **Blocks:** [sase-mg.2](sase-mg.2.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mg.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mg.1/README.md) | [sase-mg.1](sase-mg.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7acf607`](https://github.com/sase-org/sase-core/commit/7acf60737880ca56eb2745ea18b0e9a2c4e40f88) | feat: index agent output variable history | [sase-mg.1](sase-mg.1.md) | 2026-08-15 15:59:10 EDT |

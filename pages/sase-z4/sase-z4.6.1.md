# Bead: sase-z4.6.1 — Correct numeric fitting and explicit claim lineage in Rust

[Bead Pages](../README.md) / [sase-z4.6](sase-z4.6.md) / sase-z4.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.land.md) · **Assignee:** `sase-z4.6.1` · **Size:** medium
**Created:** 2026-09-10 08:15:40 EDT · **Closed:** 2026-09-10 08:45:45 EDT
**Plan:** [202609/weighted\_capacity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_landing_repairs.md)

## Description

capacity-policy: fix decimal-boundary admission, model serial claim ownership through parallel predecessors, and expose authoritative admission and parked-order decisions to host consumers.

## Notes

[2026-09-10T12:45:45Z · sase-z4.6.1] Implemented Rust runner-capacity repairs in linked sase-core: schema v2 candidate decisions, explicit lineage ownership, proposed-total capacity fit, and shared parked ordering. Verified cargo test -p sase_core runner_capacity --lib; cargo test -p sase_core_py directive_contract_and_completion_bindings_return_plain_json_shapes --lib; env LD_LIBRARY_PATH=/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib just check; git diff --check; sase bead epic-symbols sase-z4.6.1 reported no entries.

## Dependencies

- **Blocks:** [sase-z4.6.2](sase-z4.6.2.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.6.1/README.md) | [sase-z4.6.1](sase-z4.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8b672ab`](https://github.com/sase-org/sase-core/commit/8b672ab09b2e4351cfa0f0f243ea71e68d71c3a2) | fix(runner-capacity): repair weighted claim lineage | [sase-z4.6.1](sase-z4.6.1.md) | 2026-09-10 08:47:09 EDT |

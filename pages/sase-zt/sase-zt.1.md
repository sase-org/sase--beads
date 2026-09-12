# Bead: sase-zt.1 — Rust admission contract — capacity is the limit

[Bead Pages](../README.md) / [sase-zt](README.md) / sase-zt.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.06.f0` · **Assignee:** `sase-zt.1` · **Size:** medium
**Created:** 2026-09-12 10:33:28 EDT · **Closed:** 2026-09-12 11:40:26 EDT
**Plan:** [202609/queue\_capacity\_budget.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_budget.md)

## Description

core: rename the persisted capacity field to `queue_capacity`, evaluate each waiter against its own admission limit instead of a shared global limit, reject unsatisfiable authored capacity at parse time, translate legacy `capacity=0` records, and gate all of it behind the sunset flag.

## Notes

[2026-09-12T15:39:49Z · sase-zt.1] PROPOSED FOLLOW-UP: Make check.sh skip Python interpreters without loadable libpython - default just check chose python3.14 but PyO3 tests failed loading libpython3.14.so.1.0; PYO3_PYTHON=/usr/bin/python3 just check passed.

[2026-09-12T15:40:26Z · sase-zt.1] Implemented Rust queue_capacity budget contract in sase-core; verified cargo test -p sase_core queue_directive --lib, cargo test -p sase_core runner_capacity --lib, cargo test -p sase_core_py directive_contract_and_completion_bindings_return_plain_json_shapes --lib, and PYO3_PYTHON=/usr/bin/python3 just check. Default just check fails on this host because python3.14 lacks libpython3.14.so.1.0; follow-up noted.

## Dependencies

- **Blocks:** [sase-zt.2](sase-zt.2.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.1/README.md) | [sase-zt.1](sase-zt.1.md) | 0 |

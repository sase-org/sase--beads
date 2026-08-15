# Bead: sase-m9.2.1.1 — Atomic proc schema and lifecycle

[Bead Pages](../README.md) / [sase-m9.2.1](sase-m9.2.1.md) / sase-m9.2.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.2.md) · **Assignee:** `sase-m9.2.1.1` · **Size:** medium
**Created:** 2026-08-15 06:14:41 EDT · **Closed:** 2026-08-15 06:51:04 EDT
**Plan:** [202608/unified\_proc\_shell\_platform\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_proc_shell_platform_1.md)

## Description

proc-store-lifecycle: extend the Rust proc wire and Python parity models with additive/defaulted proc-shell, ownership, timeout, result, stop, and settlement fields; split permissive legacy reads from strict new-write validation; and replace generic append/update ownership with locked reserve, stop-request, supervisor-claim, and single-owner finish operations. Enforce immutable non-empty argv, active shell-name and concurrency-key conflicts, idempotent fingerprint replay, explicit supported schema versions, and settling-before-terminal invariants while keeping legacy command/tui/detached and commandless TUI rows readable. Add Rust, PyO3/wire-parity, and Python facade tests for concurrent reservations, invalid transitions, replay, legacy parsing, and retention ownership boundaries.

## Notes

[2026-08-15T10:51:04Z · sase-m9.2.1.1] Implemented schema-v3 proc-shell lifecycle in linked sase-core and Python facade; verified with just install, focused Python proc tests, just check, cargo test -p sase_core procs::store, cargo test -p sase_core --test python_wire_parity, cargo test -p sase_core_py proc_store, and git diff --check in both repos.

[2026-08-15T10:52:26Z · sase-m9.2.1.1] Implemented proc-shell lifecycle schema v3 across sase-core and Python facade; verified with just install, just check, focused Python proc tests, focused Rust store/wire/PyO3 tests, and git diff --check in both repos.

## Dependencies

- **Blocks:** [sase-m9.2.1.2](sase-m9.2.1.2.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.1/README.md) | [sase-m9.2.1.1](sase-m9.2.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6d7000a`](https://github.com/sase-org/sase-core/commit/6d7000ac8d07638f9541666de1edc09dcfd8574e) | feat(procs): add proc-shell lifecycle operations | [sase-m9.2.1.1](sase-m9.2.1.1.md) | 2026-08-15 06:53:32 EDT |
| sase | [`11072ba`](https://github.com/sase-org/sase/commit/11072ba5d56ba1968bf7c2f16df38ab31ff92c38) | feat(procs): expose proc-shell lifecycle facade | [sase-m9.2.1.1](sase-m9.2.1.1.md) | 2026-08-15 06:54:25 EDT |

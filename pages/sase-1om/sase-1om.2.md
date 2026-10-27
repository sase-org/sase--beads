# Bead: sase-1om.2 — Per-record capacity accounting in the Rust snapshot

[Bead Pages](../README.md) / [sase-1om](README.md) / sase-1om.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5e.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5e.linker.w0.md) · **Assignee:** `sase-1om.2` · **Size:** medium
**Created:** 2026-10-26 20:19:44 EDT · **Closed:** 2026-10-26 21:42:43 EDT
**Plan:** [202610/machine\_capacity\_transparency.md](https://github.com/sase-org/sase--plans/blob/main/202610/machine_capacity_transparency.md)

## Description

core-accounting: in sase-core, add an accounting list (state, charged weight, weight source, claim, reason code) covering every request record, a top-level validity flag, and a monitor-inherited weight input; bump the schema version, update the binding, and adapt sase's record builders and legacy fallback.

## Notes

[2026-10-27T01:42:33Z · sase-1om.2--1] PROPOSED FOLLOW-UP: sase-core parallel-gate flake listener_creates_private_socket_and_rejects_symlink failed once under sase tool run check (AlreadyRunning) and passes in isolation plus the ipc module together; already tracked by sase-1gz, no phase action.

[2026-10-27T01:42:43Z · sase-1om.2--1] core-accounting complete: Rust accounting[] with one entry per record (holding/riding_claim/waiting/not_holding/unknown), charged_weight, effective_weight, weight_source, claim links, reason codes, plus accounting_valid=false on fail-closed; queue_weight_inherited input with monitor override marker in agent_scan and Python builders; schema 7->8 with binding test updates; sase legacy fallback strips the new field. Verified: sase_core runner_capacity 54 tests pass, new accounting tests pass, sase test_runner_slots_accounting 2 pass, ruff+mypy clean on touched files; sase-core just check 242 pass with sole failure the known sase-1gz parallel-gate flake (passes isolated).

## Dependencies

- **Blocks:** [sase-1om.3](sase-1om.3.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1om.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1om.2.md) | [sase-1om.2](sase-1om.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f1ea08f`](https://github.com/sase-org/sase-core/commit/f1ea08fbdeb7fe40271b369892c91750a0b5c947) | feat!: per-record capacity accounting in Rust snapshot | [sase-1om.2](sase-1om.2.md) | 2026-10-26 21:44:10 EDT |
| sase | [`4a64ff9`](https://github.com/sase-org/sase/commit/4a64ff9a28e859e92badc9eb6206a78555ccccfd) | feat: adapt record builders for core capacity accounting | [sase-1om.2](sase-1om.2.md) | 2026-10-26 22:34:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1om.2--1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1om.2.md

<!-- sase:referenced-by:end -->

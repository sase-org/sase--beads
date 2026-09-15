# Bead: sase-xe.16.11.7.16.2 — Capability-set validation honors claimed v1 read-compatibility

[Bead Pages](../README.md) / [sase-xe.16.11.7.16](sase-xe.16.11.7.16.md) / sase-xe.16.11.7.16.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.01](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.01.md) · **Assignee:** `sase-xe.16.11.7.16.2` · **Size:** medium
**Created:** 2026-09-14 16:25:30 EDT · **Closed:** 2026-09-15 07:56:01 EDT
**Plan:** [202609/fleet\_ghost\_rows\_readcompat.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_ghost_rows_readcompat.md)

## Description

caps-readcompat: in sase-core fleet_contract.rs, stop rejecting older-but-readable capability sets — the normalized-equality check must ignore the schema_version stamp that CapabilitySetWire::normalized rewrites to the current version — audit the file for the same normalize-then-strict-equality pattern on other versioned wires, and add regression tests proving a v1 summary envelope yields rows instead of fleet_envelope_invalid while unnormalized content is still rejected. Full core checks including PyO3.

## Notes

[2026-09-15T11:56:01Z · sase-xe.16.11.7.16.2--1] Audit: only resolved agent summary validation had the normalize-then-strict-equality bug; owner facts normalize capabilities without strict equality. Verified: cargo test -p sase_core fleet_contract --lib passed 46 tests after edits; just check in sase-core completed exit 0; sase bead epic-symbols sase-xe.16.11.7.16.2 reported no entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.16.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-xe.16.11.7.16.2.md) | [sase-xe.16.11.7.16.2](sase-xe.16.11.7.16.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4426269`](https://github.com/sase-org/sase-core/commit/4426269c4f1e8d5b7a0a157b887cd6b0d7a46f74) | fix(fleet): accept compatible capability summaries | [sase-xe.16.11.7.16.2](sase-xe.16.11.7.16.2.md) | 2026-09-15 07:57:46 EDT |

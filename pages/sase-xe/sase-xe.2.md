# Bead: sase-xe.2 — Portable identity, resolved records, and operation contracts in sase-core

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.2` · **Size:** large
**Created:** 2026-09-06 14:06:40 EDT · **Closed:** 2026-09-06 16:06:48 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

identity-contracts: define per-user installation identity, origin/agent/family/run locators, versioned resolved summary and detail record types, capability sets, the single running-count definition, the store-generation-plus-sequence cursor, and serializable connection-plan and operation-key types in the transport-free sase_core domain crate, exposed through the existing PyO3 binding.

## Notes

[2026-09-06T20:06:48Z · sase-xe.2] Implemented fleet identity/contracts in linked sase-core and exposed PyO3 fleet_* bindings. Evidence: core cargo focus tests passed; linked core just check passed with PYO3_PYTHON/LD_LIBRARY_PATH set for uv Python; primary focused fleet smoke + validate_sase_core_rs tests passed; tools/validate_sase_core_rs passed against linked core; primary just check passed; epic-symbols reported no entries. Revision-pin evidence: primary core-floor probe reports the new fleet bindings blocked_unpublished until host-owned linked-core commit/publish, so no unrelated remote HEAD was pinned here.

## Dependencies

- **Blocks:** [sase-xe.3](sase-xe.3.md) ◐ · ⧖ 2026-09-06
- **Blocks:** [sase-xe.4](sase-xe.4.md) ◐ · ⧖ 2026-09-06
- **Blocks:** [sase-xe.7](sase-xe.7.md) ◐ · ⧖ 2026-09-06
- **Blocks:** [sase-xe.9](sase-xe.9.md) ◐ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.2.md) | [sase-xe.2](sase-xe.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`27442bd`](https://github.com/sase-org/sase/commit/27442bd8e1fd96ed2e2f3b1b9a43bb27ab5e7d66) | test(fleet): cover portable contract bindings | [sase-xe.2](sase-xe.2.md) | 2026-09-06 16:10:16 EDT |

# Bead: sase-xe.16.11.7.16.5.1 — Align owner presentation with local family history

[Bead Pages](../README.md) / [sase-xe.16.11.7.16.5](sase-xe.16.11.7.16.5.md) / sase-xe.16.11.7.16.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-xe.16.11.7.16.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-xe.16.11.7.16.land.md) · **Assignee:** `sase-xe.16.11.7.16.5.1` · **Size:** medium
**Created:** 2026-09-15 08:35:17 EDT · **Closed:** 2026-09-15 08:54:30 EDT
**Plan:** [202609/fleet\_ghost\_rows\_remaining.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_ghost_rows_remaining.md)

## Description

owner-presentation-parity: suppress orphan terminal family members in the shared Rust presentation policy while preserving active and paginated families.

## Notes

[2026-09-15T12:54:30Z · sase-xe.16.11.7.16.5.1] Implemented family-member terminal suppression in sase-core fleet presentation and gateway owner reads; verified cargo test -p sase_core family_member --lib, cargo test -p sase_gateway members --lib, and just check in sase-core.

## Dependencies

- **Blocks:** [sase-xe.16.11.7.16.5.4](sase-xe.16.11.7.16.5.4.md) ✓ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.16.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-xe.16.11.7.16.5.1/README.md) | [sase-xe.16.11.7.16.5.1](sase-xe.16.11.7.16.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@579283d`](https://github.com/sase-org/sase-core/commit/579283deed524457999b61e412025955bad3916c) | fix(fleet): suppress terminal family member rows | [sase-xe.16.11.7.16.5.1](sase-xe.16.11.7.16.5.1.md) | 2026-09-15 08:56:39 EDT |

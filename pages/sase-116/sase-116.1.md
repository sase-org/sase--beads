# Bead: sase-116.1 — Shared Rust bead target resolution

[Bead Pages](../README.md) / [sase-116](README.md) / sase-116.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0l4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0l4.md) · **Assignee:** `sase-116.1` · **Size:** medium
**Created:** 2026-09-15 09:03:31 EDT · **Closed:** 2026-09-15 10:37:04 EDT
**Plan:** [202609/global\_bead\_id\_resolution.md](https://github.com/sase-org/sase--plans/blob/main/202609/global_bead_id_resolution.md)

## Description

core-routing: implement tested Rust routing policy and bindings, add a thin Python discovery adapter, and migrate show to the shared resolver while preserving its presentation contract.

## Notes

[2026-09-15T14:37:04Z · sase-116.1] Implemented Rust-backed bead target routing and Python show integration; verified linked sase-core just check with Python 3.14 LD_LIBRARY_PATH, main just check, focused route/show/pager tests, Symvision, and no epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-116.2](sase-116.2.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-116.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-116.1/README.md) | [sase-116.1](sase-116.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`df87d68`](https://github.com/sase-org/sase/commit/df87d68dcbc6628e21bd4a4c75f8eb994cbf37ea) | feat(bead): route show targets through shared resolver | [sase-116.1](sase-116.1.md) | 2026-09-15 10:38:53 EDT |
| sase-core | [`sase-core@dd64c84`](https://github.com/sase-org/sase-core/commit/dd64c845aff247a9a74d00d50eac15a1ea827824) | feat(bead): add target routing policy | [sase-116.1](sase-116.1.md) | 2026-09-15 10:41:12 EDT |

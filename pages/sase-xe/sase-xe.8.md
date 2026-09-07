# Bead: sase-xe.8 — sase machine CLI group and sase init enrollment

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.8` · **Size:** large
**Created:** 2026-09-06 14:06:45 EDT · **Closed:** 2026-09-06 21:00:57 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

machine-cli: add the sase machine command group (add, discover, list, remove, rename, repair, status) wired through the parser registry with the default-list convention, an init-registry spec that offers remote-machine enrollment during sase init, and doctor checks for enrolled machine records.

## Notes

[2026-09-07T01:00:57Z · sase-xe.8] Implemented machine CLI enrollment plan: added dispatch machine config, credential store, fleet client, machine CLI/init integration, dispatch doctor checks, schema/default config updates, completion snapshot updates, and focused tests. Verified with SASE_CORE_WHEEL=/home/bryan/.sase/cache/sase-core-wheels/0e75345e2c934f04b930fc757785d25c0116bd0d7de9ed6d67250e9684efead0/sase_core_rs-0.32.31-cp312-abi3-manylinux_2_39_x86_64.whl just check; scoped lane escalated to the full suite and passed.

## Dependencies

- **Blocks:** [sase-xe.12](sase-xe.12.md) ✓ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.4](sase-xe.4.md) ✓ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.7](sase-xe.7.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.8.md) | [sase-xe.8](sase-xe.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`09c9325`](https://github.com/sase-org/sase/commit/09c93253dc76bb71c71ee4e855de7998172abb73) | feat(dispatch): add machine enrollment CLI | [sase-xe.8](sase-xe.8.md) | 2026-09-06 21:02:29 EDT |

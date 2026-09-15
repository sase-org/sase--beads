# Bead: sase-zw.8.7.5 — Make inventory bounded and accurate about ownership and coverage

[Bead Pages](../README.md) / [sase-zw.8.7](sase-zw.8.7.md) / sase-zw.8.7.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zw.8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.8.land.md) · **Assignee:** `sase-zw.8.7.5` · **Size:** medium
**Created:** 2026-09-14 16:48:15 EDT · **Closed:** 2026-09-15 13:15:10 EDT
**Plan:** [202609/disk\_retention\_final\_safety.md](https://github.com/sase-org/sase--plans/blob/main/202609/disk_retention_final_safety.md)

## Description

inventory: move shared inventory classification to Rust, apply a whole-pass budget, resolve actual owned roots and configured horizons, and account for overlap and incomplete scans.

## Notes

[2026-09-15T17:15:10Z · sase-zw.8.7.5] Verified focused disk-footprint/validator pytest (33 passed), installed binding validator, real collect_disk_footprint smoke, linked sase-core just check with LD_LIBRARY_PATH for uv Python, main just check with full-suite escalation, git diff --check in both repos, and no epic-symbol entries remained.

## Dependencies

- **Depends on:** [sase-zw.8.7.4](sase-zw.8.7.4.md) ✓ · ⧖ 2026-09-14
- **Blocks:** [sase-zw.8.7.6](sase-zw.8.7.6.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.8.7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.8.7.5/README.md) | [sase-zw.8.7.5](sase-zw.8.7.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`028c513`](https://github.com/sase-org/sase/commit/028c5137beeed48abef3bf9cc38ce9918423952a) | fix(disk): bound inventory coverage classification | [sase-zw.8.7.5](sase-zw.8.7.5.md) | 2026-09-15 13:17:09 EDT |
| sase-core | [`sase-core@fd7bc24`](https://github.com/sase-org/sase-core/commit/fd7bc243cec73e0c5645950dc06f6f16e65f86b1) | feat(disk): add inventory classification contract | [sase-zw.8.7.5](sase-zw.8.7.5.md) | 2026-09-15 13:20:08 EDT |

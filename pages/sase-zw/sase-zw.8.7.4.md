# Bead: sase-zw.8.7.4 — Apply dependency-preserving repair rules to normal borrower reuse

[Bead Pages](../README.md) / [sase-zw.8.7](sase-zw.8.7.md) / sase-zw.8.7.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zw.8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.8.land.md) · **Assignee:** `sase-zw.8.7.4` · **Size:** medium
**Created:** 2026-09-14 16:48:14 EDT · **Closed:** 2026-09-15 12:06:47 EDT
**Plan:** [202609/disk\_retention\_final\_safety.md](https://github.com/sase-org/sase--plans/blob/main/202609/disk_retention_final_safety.md)

## Description

objects: prevent healthy checkout reuse from rewriting alternates without eligibility, source connectivity and rollback guarantees.

## Notes

[2026-09-15T16:06:47Z · sase-zw.8.7.4] Implemented Rust/Python dependency-preserving Git object-sharing reuse guards; verified schema probe 2/2, cargo test -p sase_core git_object_sharing, pytest tests/workspace_provider/test_git_object_sharing.py, core just check with LD_LIBRARY_PATH, and main just check.

## Dependencies

- **Depends on:** [sase-zw.8.7.3](sase-zw.8.7.3.md) ✓ · ⧖ 2026-09-14
- **Blocks:** [sase-zw.8.7.5](sase-zw.8.7.5.md) ✓ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.8.7.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.8.7.4/README.md) | [sase-zw.8.7.4](sase-zw.8.7.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4e18cf5`](https://github.com/sase-org/sase/commit/4e18cf50e102659b0b717ac4dc45616fc1a1e730) | fix(workspace): guard object-sharing reuse | [sase-zw.8.7.4](sase-zw.8.7.4.md) | 2026-09-15 12:08:41 EDT |
| sase-core | [`sase-core@e6d08ad`](https://github.com/sase-org/sase-core/commit/e6d08ad68fb26108cac0144713905e3e32ce1cb9) | fix(objects): guard existing borrower repoints | [sase-zw.8.7.4](sase-zw.8.7.4.md) | 2026-09-15 12:11:15 EDT |

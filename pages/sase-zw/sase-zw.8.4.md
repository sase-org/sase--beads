# Bead: sase-zw.8.4 — Preserve shared-object dependencies throughout repair and reuse

[Bead Pages](../README.md) / [sase-zw.8](sase-zw.8.md) / sase-zw.8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zw.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.land.md) · **Assignee:** `sase-zw.8.4` · **Size:** medium
**Created:** 2026-09-13 18:40:41 EDT · **Closed:** 2026-09-14 10:47:04 EDT
**Plan:** [202609/disk\_footprint\_remaining\_work.md](https://github.com/sase-org/sase--plans/blob/main/202609/disk_footprint_remaining_work.md)

## Description

objects: complete Rust-owned sharing and repair safety, retain foreign alternates, and prevent failed borrower recovery from deleting local work.

## Notes

[2026-09-14T14:43:48Z · sase-zw.8.4] PROPOSED FOLLOW-UP: Ambient verification failures outside object-sharing phase — just check is currently blocked by Symvision private imports in monitor/gate shell stores; escalated full test lane also fails existing artifact-retention policy/audit tests; cargo clippy hits an unrelated too_many_arguments lint in crates/sase_core/src/procs/runtime.rs.

[2026-09-14T14:47:04Z · sase-zw.8.4] Verified object-sharing planner and borrower repair with .venv/bin/pytest -q tests/workspace_provider/test_git_object_sharing.py tests/main/test_workspace_handler_cleanup_repair.py (22 passed), cargo test -p sase_core git_object_sharing (5 passed), .venv/bin/python tools/validate_sase_core_rs --sase-core-dir sase/repos/linked/sase-core, and sase bead epic-symbols sase-zw.8.4 (no entries). just check was run and is blocked by unrelated Symvision private-import failures; the escalated full test lane failures were recorded as a PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-zw.8.3](sase-zw.8.3.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-zw.8.5](sase-zw.8.5.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.8.4/README.md) | [sase-zw.8.4](sase-zw.8.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`16ee9c2`](https://github.com/sase-org/sase/commit/16ee9c2336456f25e1f1cb4f6650bdd58dd9ff92) | fix(workspace): preserve shared object dependencies | [sase-zw.8.4](sase-zw.8.4.md) | 2026-09-14 10:49:04 EDT |
| sase-core | [`sase-core@afe7b70`](https://github.com/sase-org/sase-core/commit/afe7b70dbede84164be66c55b62f2b912262a87f) | feat(core): plan git object sharing rewrites | [sase-zw.8.4](sase-zw.8.4.md) | 2026-09-14 10:51:31 EDT |

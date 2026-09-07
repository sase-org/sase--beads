# Bead: sase-xe.12 — The %dispatch directive and reliable remote launch

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.12` · **Size:** large
**Created:** 2026-09-06 14:06:47 EDT · **Closed:** 2026-09-07 02:34:54 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

dispatch-launch: add %dispatch:<machine> to the dual-sourced directive vocabulary, intercept routing in the shared launch trunk before any target-side allocation, persist source intent with an operation key, send a portable launch request validated and admitted on the target, bind the receipt, auto-follow the resulting family, and reconcile lost replies without ever falling back to another machine.

## Notes

[2026-09-07T06:34:54Z · sase-xe.12] Auto-closed by `sase stitch create` after create_commit landed 50b1405f4 ("feat(dispatch): launch agents on remote machines"). No verification is implied by this note. Reopen with `sase bead open sase-xe.12`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-xe.10](sase-xe.10.md) ✓ · ⧖ 2026-09-06
- **Blocks:** [sase-xe.13](sase-xe.13.md) ◐ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.6](sase-xe.6.md) ✓ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.8](sase-xe.8.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.12](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.12.md) | [sase-xe.12](sase-xe.12.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`50b1405`](https://github.com/sase-org/sase/commit/50b1405f4268eae9e84302bb3f32bc429fe09d85) | feat(dispatch): launch agents on remote machines | [sase-xe.12](sase-xe.12.md) | 2026-09-07 02:32:38 EDT |
| sase-core | [`sase-core@06fb5c3`](https://github.com/sase-org/sase-core/commit/06fb5c38ec612253ce1d6ced75e4a4ae89278ed4) | feat(fleet): add remote launch dispatch contract | [sase-xe.12](sase-xe.12.md) | 2026-09-07 02:36:29 EDT |

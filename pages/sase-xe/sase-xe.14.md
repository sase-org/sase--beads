# Bead: sase-xe.14 — Remote questions, gates, and notification deduplication

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.14

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.14` · **Size:** large
**Created:** 2026-09-06 14:06:49 EDT · **Closed:** 2026-09-07 11:27:05 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

attention-parity: surface remote question and gate attention in Focus promptly, answer questions and approve gates through consume-once mutation semantics with an already-answered result for a losing controller, and deduplicate notifications by origin plus request identity across reconnects.

## Notes

[2026-09-07T15:27:05Z · sase-xe.14] Auto-closed by `sase stitch create` after create_commit landed 287048d60 ("feat(dispatch): surface and answer remote question/gate attention in Focus"). No verification is implied by this note. Reopen with `sase bead open sase-xe.14`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-xe.13](sase-xe.13.md) ✓ · ⧖ 2026-09-06
- **Blocks:** [sase-xe.15](sase-xe.15.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.14](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.14.md) | [sase-xe.14](sase-xe.14.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`287048d`](https://github.com/sase-org/sase/commit/287048d601b6a2003aa01e12743c2ed053c7c982) | feat(dispatch): surface and answer remote question/gate attention in Focus | [sase-xe.14](sase-xe.14.md) | 2026-09-07 11:24:08 EDT |
| sase-core | [`sase-core@b19c603`](https://github.com/sase-org/sase-core/commit/b19c6030c7c289ef26238073cc9a4c4aad24fe62) | feat(fleet): add attention contract, gateway routes, and federation ops | [sase-xe.14](sase-xe.14.md) | 2026-09-07 11:27:35 EDT |

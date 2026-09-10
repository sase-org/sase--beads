# Bead: sase-yy.4 — Automatic link writes publish as events through the machine lane

[Bead Pages](../README.md) / [sase-yy](README.md) / sase-yy.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09d.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09d.f1.md) · **Assignee:** `sase-yy.4` · **Size:** large
**Created:** 2026-09-09 11:48:17 EDT · **Closed:** 2026-09-09 16:26:27 EDT
**Plan:** [202609/artifact\_link\_events\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_events_v2.md)

## Description

event-publisher: behind a new beta flag, automatic writers enqueue events instead of dirtying agent sidecar clones, and a serialized per-project publisher batches them into the hidden host-owned clones through the existing commit choke point so the sase-yh retry ledger owns push retry.

## Notes

[2026-09-09T20:26:27Z · sase-yy.4] Auto-closed by `sase stitch create` after create_commit landed 37ab56bd9 ("feat(artifact-links): publish immutable link events"). No verification is implied by this note. Reopen with `sase bead open sase-yy.4`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-yy.3](sase-yy.3.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-yy.6](sase-yy.6.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.4.md) | [sase-yy.4](sase-yy.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`37ab56b`](https://github.com/sase-org/sase/commit/37ab56bd93a84d851c80cc5c50e63c75747f4aa6) | feat(artifact-links): publish immutable link events | [sase-yy.4](sase-yy.4.md) | 2026-09-09 16:23:43 EDT |
| sase-core | [`sase-core@1842f29`](https://github.com/sase-org/sase-core/commit/1842f29c00a9288f90d8cbc898ef8c8a40731c85) | feat(beads): support link operation ids | [sase-yy.4](sase-yy.4.md) | 2026-09-09 16:27:08 EDT |

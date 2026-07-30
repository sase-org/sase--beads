# Bead: sase-bd.1 — Closed-interval semantics in the event reducer

[Bead Pages](../README.md) / [sase-bd](README.md) / sase-bd.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bd.1` · **Size:** medium
**Created:** 2026-07-30 17:43:47 UTC · **Closed:** 2026-07-30 17:55:19 UTC
**Plan:** [202607/bead\_close\_integrity.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_close_integrity.md)

## Description

core-close-interval: make `apply_event` treat a close of an already-closed bead as an exact no-op and clear `closed_at`/`close_reason` on every transition out of closed, so duplicate close events cannot move a close timestamp and the projection converges regardless of merge order.

## Notes

[2026-07-30T17:59:09Z · sase-bd.1] Verified redundant closes preserve the first closed_at, close_reason, resolution, and updated_at; issue_opened, non-closed issue_updated, and epic_work_preclaimed clear close metadata; genuine re-close stamps a new interval; cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace all pass in sase-core at 160ff9e.

## Dependencies

- **Blocks:** [sase-bd.2](sase-bd.2.md) ✓
- **Blocks:** [sase-bd.5](sase-bd.5.md) ◐
- **Blocks:** [sase-bd.6](sase-bd.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bd.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bd.1/README.md) | [sase-bd.1](sase-bd.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@160ff9e`](https://github.com/sase-org/sase-core/commit/160ff9e7616fae351febd676792970e3dd654cc7) | fix(bead): preserve the first close in event reduction | [sase-bd.1](sase-bd.1.md) | 2026-07-30 17:55:34 |

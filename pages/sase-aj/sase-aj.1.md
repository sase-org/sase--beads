# Bead: sase-aj.1 — Idempotent claim mutations and epic-capable batch preclaim in Rust core

[Bead Pages](../README.md) / [sase-aj](README.md) / sase-aj.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-aj.1` · **Size:** medium
**Created:** 2026-07-28 20:21:32 UTC · **Closed:** 2026-07-28 20:33:28 UTC
**Plan:** [202607/beads\_commit\_consolidation.md](https://github.com/sase-org/sase--plans/blob/main/202607/beads_commit_consolidation.md)

## Description

core: make runtime claim/close/update mutations quiet no-ops when they would not change state, and extend the batch epic-work preclaim so it can include the epic bead itself with the land agent assignment.

## Notes

[2026-07-28T20:32:45Z · sase-aj.1] Implemented idempotent launch/wait/update/close mutations and epic-inclusive batch preclaim with PyO3 support. Verified with cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

## Dependencies

- **Blocks:** [sase-aj.2](sase-aj.2.md) ◐
- **Blocks:** [sase-aj.3](sase-aj.3.md) ◎
- **Blocks:** [sase-aj.4](sase-aj.4.md) ✓
- **Blocks:** [sase-aj.5](sase-aj.5.md) ◐

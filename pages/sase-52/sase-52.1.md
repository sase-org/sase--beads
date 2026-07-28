# Bead: sase-52.1 — Phase 1: Core Grammar Contract

[Bead Pages](../README.md) / [sase-52](README.md) / sase-52.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-52.1`
**Created:** 2026-06-20 18:28:13 UTC · **Closed:** 2026-06-20 19:08:16 UTC
**Plan:** [202606/alt\_brace\_syntax.md](https://github.com/sase-org/sase--plans/blob/main/202606/alt_brace_syntax.md)

## Description

Repo: ../sase-core workspace 10. Implement %{...} in the Rust launch fan-out planner before touching UI surfaces. Extend alt directive detection to include %{...}, parse branches via top-level | separators, preserve nested/quoted branch behavior, named branches, single-branch with/without variants, %model fan-out parity, and keep %alt(...)/%(...) compatibility. Add focused Rust tests. Validation: cargo fmt --all -- --check; cargo test -p sase_core fanout_planner; cargo test -p sase_core agent_launch.

## Notes

COMMIT: b62f5160d

## Dependencies

- **Blocks:** [sase-52.2](sase-52.2.md) ✓
- **Blocks:** [sase-52.3](sase-52.3.md) ✓
- **Blocks:** [sase-52.4](sase-52.4.md) ✓
- **Blocks:** [sase-52.5](sase-52.5.md) ✓
- **Blocks:** [sase-52.7](sase-52.7.md) ✓

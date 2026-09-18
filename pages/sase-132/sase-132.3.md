# Bead: sase-132.3 — Cut the bounded Tier 1 load's absolute cost

[Bead Pages](../README.md) / [sase-132](README.md) / sase-132.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0n7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0n7.md) · **Assignee:** `sase-132.3` · **Size:** large
**Created:** 2026-09-18 15:22:35 EDT
**Plan:** [202609/tui\_startup\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_startup_regression.md)

## Description

loader-diet: attribute and reverse the standalone bounded-load creep (production_bounded p50 1002 ms on 2026-09-13 to 1632 ms on 2026-09-18 at +3% archive growth), including the ~11x decode amplification (about 1,062 records decoded to return 96 rows) and index row growth, with Rust-core pushdown evaluated under the rust_core_backend_boundary rule.

## Dependencies

- **Depends on:** [sase-132.1](sase-132.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-132.7](sase-132.7.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-132.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-132.3/README.md) | [sase-132.3](sase-132.3.md) | 0 |

# Bead: sase-12y.1 — Add an atomic bulk bead-projection core API

[Bead Pages](../README.md) / [sase-12y](README.md) / sase-12y.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.0k](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.0k.md) · **Assignee:** `sase-12y.1` · **Size:** medium
**Created:** 2026-09-18 09:47:59 EDT · **Closed:** 2026-09-18 10:26:53 EDT
**Plan:** [202609/artifact\_link\_projection\_timeout.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_projection_timeout.md)

## Description

projection_batch_core: add and publish a Rust/PyO3 batch mutation that preserves the exact single-projection receipt and convergence contract while taking one bead lock, loading once, and saving once per bounded batch.

## Notes

[2026-09-18T14:26:53Z · sase-12y.1] Added set_bead_link_projections in sase-core: one lock/load/save per batch, singleton refactored through the shared apply path, PyO3 bead_set_link_projections registered. Verified mixed present/absent + directed/undirected/alias byte-equivalence with singleton, invalid-middle rollback (store unchanged), seen-receipt repair then 1-load/0-save replay, 32-request batch is 1 load/1 save vs 32/32 singleton, binding conversion/validation tests, and sase-core just check (fmt, clippy, workspace tests).

## Dependencies

- **Blocks:** [sase-12y.2](sase-12y.2.md) ◐ · ⧖ 2026-09-18
- **Blocks:** [sase-12y.3](sase-12y.3.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-12y.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-12y.1/README.md) | [sase-12y.1](sase-12y.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d32591f`](https://github.com/sase-org/sase-core/commit/d32591f6963247b81664772e55a8543c5912ec6a) | feat(bead): add atomic bulk link-projection mutation | [sase-12y.1](sase-12y.1.md) | 2026-09-18 10:29:48 EDT |

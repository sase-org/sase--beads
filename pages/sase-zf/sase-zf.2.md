# Bead: sase-zf.2 — Rust-backed committed-query engine behind a sunset flag

[Bead Pages](../README.md) / [sase-zf](README.md) / sase-zf.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0iy](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0iy.md) · **Assignee:** `sase-zf.2` · **Size:** medium
**Created:** 2026-09-10 18:01:47 EDT · **Closed:** 2026-09-10 20:03:22 EDT
**Plan:** [202609/agents\_query\_unification.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_query_unification.md)

## Description

live-engine: swap the Agents tab committed-query parse/evaluate path to the agents-live profile behind a new sunset feature flag, using an off-thread Rust corpus index, tree-preserving match masks, and last-good error handling.

## Notes

[2026-09-11T00:03:22Z · sase-zf.2] Auto-closed by `sase stitch create` after create_commit landed 699d2adf7 ("feat(agents-tab): add Rust-backed committed-query engine behind sunset flag"). No verification is implied by this note. Reopen with `sase bead open sase-zf.2`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-zf.1](sase-zf.1.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-zf.3](sase-zf.3.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-zf.4](sase-zf.4.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zf.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zf.2/README.md) | [sase-zf.2](sase-zf.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`699d2ad`](https://github.com/sase-org/sase/commit/699d2adf7a8ab928c0bcfa57dedfb54357f9189c) | feat(agents-tab): add Rust-backed committed-query engine behind sunset flag | [sase-zf.2](sase-zf.2.md) | 2026-09-10 20:02:31 EDT |

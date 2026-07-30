# Bead: sase-au.2 — XPrompt aggregation section in the run-statistics wire and query

[Bead Pages](../README.md) / [sase-au](README.md) / sase-au.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-au.2` · **Size:** medium
**Created:** 2026-07-29 16:26:16 UTC · **Closed:** 2026-07-29 16:49:03 UTC
**Plan:** [202607/xprompt\_statistics.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_statistics.md)

## Description

core-stats: in sase-core, fold the projected xprompt usage of every in-window run into a new optional xprompts section of the run-statistics response, with ranked rows, bounded model/project/partner cross-tabs, and an optional focused single-xprompt payload driven by new request knobs.

## Notes

[2026-07-29T16:49:03Z · sase-au.2] Implemented run-statistics wire schema v4 xprompt request/response fields and in-window aggregation with deterministic ranked rows, bounded model/project/partner cross-tabs, and focused provider/tribe/project/partner/bucket detail. Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

[2026-07-29T16:50:13Z · sase-au.2] Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace; schema v4 xprompt aggregation and Python binding contract tests pass.

## Dependencies

- **Depends on:** [sase-au.1](sase-au.1.md) ✓
- **Blocks:** [sase-au.6](sase-au.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-au.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-au.2/README.md) | [sase-au.2](sase-au.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@60eccf6`](https://github.com/sase-org/sase-core/commit/60eccf66f9a29a5fa3b5d6929ddbe66f5354bda7) | feat(stats): aggregate xprompt usage | [sase-au.2](sase-au.2.md) | 2026-07-29 16:51:12 |

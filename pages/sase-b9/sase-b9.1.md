# Bead: sase-b9.1 — Rust core: consumption ledger reading, aggregation, and the unused query filter

[Bead Pages](../README.md) / [sase-b9](README.md) / sase-b9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b9.1` · **Size:** medium
**Created:** 2026-07-30 14:36:37 UTC · **Closed:** 2026-07-30 14:48:17 UTC
**Plan:** [202607/artifact\_consumption\_ledger.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_consumption_ledger.md)

## Description

core-ledger: add a tolerant consumption-log reader, a per-reference aggregation summary, an `unused_only` artifact-file query filter applied before the row limit, and a fragment-free reference renderer, all exposed through `sase_core_rs`.

## Notes

[2026-07-30T14:48:17Z · sase-b9.1] Implemented the tolerant Rust consumption-log reader, per-reference aggregation, consumed file-ref set, pre-limit unused_only artifact query filter with query wire v3, fragment-free renderer coverage, and sase_core_rs summary/schema bindings. Verified with cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, and git diff --check; tests cover malformed/unsupported/missing ledger rows, repeated vs distinct-agent counts, restricted refs, timezone-aware first/last timestamps, missing/unreadable ledgers, unused filtering before limit, binding handshakes, and bug refs containing #.

## Dependencies

- **Blocks:** [sase-b9.2](sase-b9.2.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b9.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b9.1/README.md) | [sase-b9.1](sase-b9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`1bd3670`](https://github.com/sase-org/sase-core/commit/1bd3670481a252fa449f6d5885673eb7ecbcc427) | feat: add artifact consumption ledger queries | [sase-b9.1](sase-b9.1.md) | 2026-07-30 14:49:24 |

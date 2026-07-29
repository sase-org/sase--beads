# Bead: sase-ax.1 — Artifact-file index contract and query API in sase-core

[Bead Pages](../README.md) / [sase-ax](README.md) / sase-ax.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ax.1` · **Size:** medium
**Created:** 2026-07-29 21:06:34 UTC · **Closed:** 2026-07-29 21:18:57 UTC
**Plan:** [202607/artifact\_read\_cli.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_read_cli.md)

## Description

core-index-contract: extract the index parser into a tolerant full-record module in the sase-core repo, accept envelope schema versions 1..=2, add a filterable query function reusing plan-search date parsing, and expose artifact_files_query plus a wire-schema handshake through the PyO3 bindings.

## Notes

[2026-07-29T21:18:57Z · sase-ax.1] Implemented the tolerant full-record artifact-file index parser and shared v1..=v2 resolution path, filterable newest-first query API with plan-search date-form parity, and PyO3 artifact_files_query plus wire-schema handshake. Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, dedicated v1/v2 file-resolution coverage, and PyO3 binding registration/row-shape tests.

## Dependencies

- **Blocks:** [sase-ax.3](sase-ax.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-ax.1 | [sase-ax.1](sase-ax.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`ad900a7`](https://github.com/sase-org/sase-core/commit/ad900a770cabaa168a3ad521f724f42e8f9c3c25) | feat(artifact): add artifact file query API | [sase-ax.1](sase-ax.1.md) | 2026-07-29 21:20:30 |

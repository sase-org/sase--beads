# Bead: sase-75.1 — Rust core and LSP trigger contract

[Bead Pages](../README.md) / [sase-75](README.md) / sase-75.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-75.1`
**Created:** 2026-07-19 12:38:37 UTC
**Plan:** [202607/space\_plus\_vcs\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/space_plus_vcs_completion.md)

## Description

'Rust core and LSP trigger contract' section: replace hash-plus and BOF-only detection with the shared bare-plus-at-BOF-or-after-space contract, then update Rust completion and LSP coverage.

## Notes

Implemented the Rust core and xprompt LSP +query contract: triggers only at document offset zero or immediately after literal ASCII space; removed hash-plus handling and variable prefix logic; updated canonical edit/filtering coverage, automatic/manual LSP coverage, ChangeSpec rows, cursor-inside-token cases, and negative newline/tab/glued/operator cases. Verified with cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

## Dependencies

- **Blocks:** [sase-75.2](sase-75.2.md) ✓

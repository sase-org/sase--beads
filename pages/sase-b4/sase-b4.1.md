# Bead: sase-b4.1 — Shared kind-stage file-row gate in sase-core

[Bead Pages](../README.md) / [sase-b4](README.md) / sase-b4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b4.1` · **Size:** medium
**Created:** 2026-07-30 11:15:04 UTC · **Closed:** 2026-07-30 11:25:22 UTC
**Plan:** [202607/at\_reference\_file\_row\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202607/at_reference_file_row_gate.md)

## Description

core-gate: add an at-reference menu options wire plus a `files_suppressed` menu flag to `sase_core`, suppress Kind-stage path rows when an artifact kind prefix-matches the query unless the caller opts in, expose the option through the `sase_core_rs` binding, and map an `Invoked` LSP completion request to the opt-in.

## Notes

[2026-07-30T11:25:22Z · sase-b4.1] Implemented the additive at-reference menu options wire and files_suppressed signal in sase-core; gated Kind-stage file rows on tier-0 kind prefix matches with explicit include_files opt-in; exposed options through sase_core_rs; mapped LSP CompletionTriggerKind::INVOKED to the opt-in; added Rust, Python binding, and LSP coverage. Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, and git diff --check.

[2026-07-30T11:26:48Z · sase-b4.1] Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets --all-features -- -D warnings, cargo test --workspace, and git diff --check in sase-core.

## Dependencies

- **Blocks:** [sase-b4.2](sase-b4.2.md) ✓
- **Blocks:** [sase-b4.3](sase-b4.3.md) ✓

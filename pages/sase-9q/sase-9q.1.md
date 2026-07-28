# Bead: sase-9q.1 — Raw-placeholder rules and transforms in sase-core

[Bead Pages](../README.md) / [sase-9q](README.md) / sase-9q.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9q.1` · **Size:** medium
**Created:** 2026-07-26 10:06:49 UTC
**Plan:** [sase/repos/plans/202607/raw\_placeholder\_inputs.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/raw_placeholder_inputs.md)

## Description

'Phase core' section: add the raw/literal classification, raw-field summaries, span-safe substitution, and input-name slugging to sase-core plus their Python bindings.

## Notes

Implemented shared prompt literal-zone exposure; raw/literal PlaceholderSpan classification and raw-only completion; ordered raw field summaries with bounded context; single-pass span-safe substitution; deterministic Unicode input-name slugging; Python bindings and smoke coverage; and updated the LSP integration fixture for raw-only completion. Verified with cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace in sase-core. Downstream phases must run just install in the sase checkout first so sase_core_rs is rebuilt from the linked sase-core checkout.

## Dependencies

- **Blocks:** [sase-9q.2](sase-9q.2.md) ✓

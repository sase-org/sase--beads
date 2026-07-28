# Bead: sase-2b.2 — Move Definition Resolution Into Core Editor Logic

[Bead Pages](../README.md) / [sase-2b](README.md) / sase-2b.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-2b.2`
**Created:** 2026-05-07 16:53:24 UTC
**Plan:** [202605/xprompt\_lsp\_jump\_definition.md](https://github.com/sase-org/sase--plans/blob/main/202605/xprompt_lsp_jump_definition.md)

## Description

Expose a pure Rust editor definition resolver that shares token extraction and normalization with hover/completion and resolves catalog definition_path values.

## Notes

Implemented pure Rust editor definition resolution in ../sase-core: added editor::definition::definition_at_position with DefinitionTarget, shared token normalization helpers with hover, conservative definition_path validation, and tests for inline, standalone, namespaced shorthand, slash skills, missing/invalid targets, nonexistent paths, and outside-workspace files. Verified with cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test -p sase_core editor::definition, and cargo test --workspace.

## Dependencies

- **Depends on:** [sase-2b.1](sase-2b.1.md) ✓
- **Blocks:** [sase-2b.3](sase-2b.3.md) ✓

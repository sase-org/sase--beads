# Bead: sase-2a.2 — Phase 2: Core Editor Analyzer MVP

[Bead Pages](../README.md) / [sase-2a](README.md) / sase-2a.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-2a.2`
**Created:** 2026-05-07 07:38:30 UTC
**Plan:** [202605/xprompt\_lsp\_server.md](https://github.com/sase-org/sase--plans/blob/main/202605/xprompt_lsp_server.md)

## Description

Port the duplicated editor rules into pure, testable Rust APIs under sase_core, independent of JSON-RPC/LSP.

## Notes

Implemented sase_core::editor MVP in ../sase-core: document/position helpers, token extraction and context classification, file/xprompt/directive completions, narrow xprompt argument contexts, diagnostics, hover payloads, and focused unit coverage. Verification in ../sase-core: cargo fmt --all -- --check; cargo clippy --workspace --all-targets -- -D warnings; cargo test --workspace.

## Dependencies

- **Depends on:** [sase-2a.1](sase-2a.1.md) ✓
- **Blocks:** [sase-2a.3](sase-2a.3.md) ✓
- **Blocks:** [sase-2a.8](sase-2a.8.md) ✓

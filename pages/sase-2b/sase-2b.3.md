# Bead: sase-2b.3 — Wire Standard LSP textDocument/definition

[Bead Pages](../README.md) / [sase-2b](README.md) / sase-2b.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-2b.3`
**Created:** 2026-05-07 16:53:31 UTC
**Plan:** [202605/xprompt\_lsp\_jump\_definition.md](https://github.com/sase-org/sase--plans/blob/main/202605/xprompt_lsp_jump_definition.md)

## Description

Use the core definition resolver in the xprompt LSP server and return standard Location results for supported disk-backed xprompt definitions.

## Notes

Implemented LSP definition wiring in ../sase-core: textDocument/definition and Open xprompt source now use the core editor definition resolver with definition_path. Added LSP unit coverage for outside-workspace definition files and pseudo/missing sources, plus JSON-RPC definition coverage. Verification: cargo fmt --all -- --check; cargo test -p sase_core editor::definition; cargo test -p sase_xprompt_lsp; cargo clippy --workspace --all-targets -- -D warnings; cargo test --workspace.

## Dependencies

- **Depends on:** [sase-2b.2](sase-2b.2.md) ✓
- **Blocks:** [sase-2b.4](sase-2b.4.md) ✓
- **Blocks:** [sase-2b.5](sase-2b.5.md) ✓

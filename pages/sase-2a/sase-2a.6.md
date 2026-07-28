# Bead: sase-2a.6 — Phase 6: Neovim LSP Client MVP

[Bead Pages](../README.md) / [sase-2a](README.md) / sase-2a.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-2a.6`
**Created:** 2026-05-07 07:39:00 UTC
**Plan:** [202605/xprompt\_lsp\_server.md](https://github.com/sase-org/sase--plans/blob/main/202605/xprompt_lsp_server.md)

## Description

Make sase-nvim start and use the LSP while preserving the existing public API and legacy fallback.

## Notes

Implemented opt-in sase-nvim xprompt LSP client MVP in ../sase-nvim: added lua/sase/lsp.lua, setup lsp options, completion_backend routing with legacy fallback, README docs, and headless Lua tests. Verified with nvim --headless -u NONE -l tests/completion_helpers.lua; nvim --headless -u NONE -l tests/lsp_config.lua; nvim setup smoke; LSP attach/completion smoke against ../sase-core/target/debug/sase-xprompt-lsp; git diff --check. ../sase-nvim has no Justfile or repo-level just check target.

## Dependencies

- **Depends on:** [sase-2a.3](sase-2a.3.md) ✓
- **Depends on:** [sase-2a.4](sase-2a.4.md) ✓
- **Blocks:** [sase-2a.7](sase-2a.7.md) ✓
- **Blocks:** [sase-2a.8](sase-2a.8.md) ✓

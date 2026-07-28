# Bead: sase-2b.5 — Neovim Smoke Docs And Optional Convenience Mapping

[Bead Pages](../README.md) / [sase-2b](README.md) / sase-2b.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-2b.5`
**Created:** 2026-05-07 16:53:51 UTC
**Plan:** [202605/xprompt\_lsp\_jump\_definition.md](https://github.com/sase-org/sase--plans/blob/main/202605/xprompt_lsp_jump_definition.md)

## Description

Prove the Neovim client can use the standard LSP definition provider without duplicating resolver logic, then document the workflow.

## Notes

Implemented in ../sase-nvim: added headless Lua smoke coverage that captures the SASE xprompt LSP client startup config, verifies standard Neovim vim.lsp.buf.definition is available, preserves definition client capabilities, and does not install custom textDocument/definition handlers or Lua path parsing. Updated README XPrompt LSP docs to explain that normal LSP go-to-definition (gd / vim.lsp.buf.definition()) opens disk-backed xprompt sources via the server's standard textDocument/definition response. Verification: nvim --headless -u NONE -n -c 'luafile tests/lsp_config.lua' -c 'qa'; nvim --headless -u NONE -n -c 'luafile tests/completion_helpers.lua' -c 'qa'. Repo-level just check not run because ../sase-nvim has no justfile (just check exits: No justfile found).

## Dependencies

- **Depends on:** [sase-2b.3](sase-2b.3.md) ✓
- **Blocks:** [sase-2b.6](sase-2b.6.md) ✓

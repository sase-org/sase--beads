# Bead: sase-2a.7 — Phase 7: Thin sase-nvim Migration And Cleanup

[Bead Pages](../README.md) / [sase-2a](README.md) / sase-2a.7

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-2a.7`
**Created:** 2026-05-07 07:39:12 UTC
**Plan:** [202605/xprompt\_lsp\_server.md](https://github.com/sase-org/sase--plans/blob/main/202605/xprompt_lsp_server.md)

## Description

Make the LSP path the normal path and remove duplicated logic from the plugin once parity is proven.

## Notes

Completed Phase 7 thin sase-nvim migration: default completion backend is now auto, LSP client is enabled by default after setup, command resolution verifies 'sase lsp --version' before selecting the wrapper and falls back to standalone/legacy behavior, legacy Lua token logic is documented as fallback-only, browse pickers remain CLI-backed until an LSP browse/catalog request exists, and README/tests cover the normal LSP path plus picker-only fallback. Verification: in ../sase-nvim ran nvim --headless -u NONE -c 'luafile tests/lsp_config.lua' -c 'qa'; nvim --headless -u NONE -c 'luafile tests/completion_helpers.lua' -c 'qa'; nvim --headless -u NONE +'set ft=markdown' +'lua package.path = vim.fn.getcwd() .. "/lua/?.lua;" .. vim.fn.getcwd() .. "/lua/?/init.lua;" .. package.path; require("sase").setup({ complete = { keymap = false } }); if require("sase.complete")._config().completion_backend ~= "auto" then error("backend not auto") end; if require("sase.lsp").can_start() then error("unexpected local lsp availability") end' +qa. No repo-level Justfile/just check target exists in ../sase-nvim.

## Dependencies

- **Depends on:** [sase-2a.6](sase-2a.6.md) ✓
- **Blocks:** [sase-2a.8](sase-2a.8.md) ✓

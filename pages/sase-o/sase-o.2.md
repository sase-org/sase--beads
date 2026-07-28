# Bead: sase-o.2 — Phase 2 — sase-nvim dispatcher skeleton + \<ctrl+t\> keymap

[Bead Pages](../README.md) / [sase-o](README.md) / sase-o.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-25 01:36:02 UTC
**Plan:** [202604/nvim\_ctrl\_t\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202604/nvim_ctrl_t_completion.md)

## Description

Repo: sase-nvim. Lay down infrastructure: lua/sase/complete.lua dispatcher, _token.lua classifier, _picker.lua shared picker plumbing, refactor existing xprompt code, plugin/sase_complete.lua opt-in keymap. Only xprompt branch wired; others stub with notify. See plans/202604/nvim_ctrl_t_completion.md Phase 2 for full details.

## Notes

Phase 2 complete. Delivered in sase-nvim:
- lua/sase/complete/_token.lua — token_under_cursor() + classify() mirroring TUI rules (file_completion.py / xprompt_completion.py)
- lua/sase/complete/_picker.lua — shared insert/restore helpers for future modes
- lua/sase/complete/xprompt.lua — thin wrapper around sase.xprompt.pick() for uniform dispatcher entry
- lua/sase/complete.lua — M.trigger() dispatcher; xprompt branch wired, file/file_history branches notify 'not yet implemented'
- lua/sase/init.lua — top-level require('sase').setup{complete = {keymap = true}}
- plugin/sase_complete.lua — load guard (keymap is opt-in via setup)
- README.md — new Setup section documenting the <C-t> dispatcher

Existing xprompt code (lua/sase/xprompt.lua, plugin/sase_xprompt.lua, telescope/_extensions/sase.lua) is untouched — :SaseXPrompts, :SaseXPromptsRefresh, and the #@ trigger continue to work unchanged. Headless smoke test verified token classifier correctness, module loading, and that <C-t> is registered in insert mode after setup({complete = {keymap = true}}). Not committed — per sase commit policy a post-completion hook will handle that.

## Dependencies

- **Blocks:** [sase-o.3](sase-o.3.md) ✓
- **Blocks:** [sase-o.4](sase-o.4.md) ✓
- **Blocks:** [sase-o.5](sase-o.5.md) ✓

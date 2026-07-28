# Bead: sase-52.6 — Phase 6: Neovim Editing Behavior

[Bead Pages](../README.md) / [sase-52](README.md) / sase-52.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-52.6`
**Created:** 2026-06-20 18:34:13 UTC · **Closed:** 2026-06-20 20:28:24 UTC
**Plan:** [202606/alt\_brace\_syntax.md](https://github.com/sase-org/sase--plans/blob/main/202606/alt_brace_syntax.md)

## Description

Repo: ../sase-nvim workspace 10. Depends on Phase 5 only for buffer eligibility helpers, not parser support. Implement %{} pairing, paired deletion, and | normalization. Add lua/sase/alt_edit.lua; register buffer-local behavior from require('sase').setup() with default-on alt_editing.enabled = true. Use InsertCharPre for { after % (insert {} and move cursor between braces) and | inside %{} (normalize padded separator, cursor before }). Buffer-local backspace/delete so deleting { in %{} also removes paired }. Reuse LSP/highlighter prompt-buffer eligibility (respect allow_all_markdown). Keep #@ picker trigger working. Add headless tests for auto-pair, paired delete, | spacing + %{foo ,bar, and baz| case, and no edits outside supported buffers. Validation: nvim --headless -u NONE -c 'set rtp+=.' -l tests/alt_edit.lua; tests/lsp_config.lua; manual smoke.

## Notes

COMMIT: 6102adafb

## Dependencies

- **Depends on:** [sase-52.5](sase-52.5.md) ✓
- **Blocks:** [sase-52.7](sase-52.7.md) ✓

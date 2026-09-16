# Bead: sase-11i.3 — Neovim legend safety and default highlight links

[Bead Pages](../README.md) / [sase-11i](README.md) / sase-11i.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0lq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0lq.md) · **Assignee:** `sase-11i.3` · **Size:** small
**Created:** 2026-09-15 21:08:40 EDT · **Closed:** 2026-09-15 22:13:10 EDT
**Plan:** [202609/xprompt\_keyword\_arg\_highlighting.md](https://github.com/sase-org/sase--plans/blob/main/202609/xprompt_keyword_arg_highlighting.md)

## Description

nvim-groups: make the glossary underline filter legend-proof, add default highlight links only where a standard token type reads poorly on a plain colorscheme, and cover the new tokens with an LSP smoke test.

## Notes

[2026-09-16T02:13:10Z · sase-11i.3] Verified with nvim --headless -u NONE -c 'set rtp+=.' -l tests/glossary_highlight.lua; nvim --headless -u NONE -c 'set rtp+=.' -l tests/xprompt_semantic_highlight.lua; nvim --headless -u NONE -c 'set rtp+=.' -l tests/lsp_argument_semantic_smoke.lua; and sase bead epic-symbols sase-11i.3 showed no leftover entries.

## Dependencies

- **Depends on:** [sase-11i.2](sase-11i.2.md) ✓ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11i.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11i.3/README.md) | [sase-11i.3](sase-11i.3.md) | 0 |

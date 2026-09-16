# Bead: sase-11i.2 — LSP semantic tokens for argument structure

[Bead Pages](../README.md) / [sase-11i](README.md) / sase-11i.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0lq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0lq.md) · **Assignee:** `sase-11i.2` · **Size:** medium
**Created:** 2026-09-15 21:08:39 EDT · **Closed:** 2026-09-15 21:58:18 EDT
**Plan:** [202609/xprompt\_keyword\_arg\_highlighting.md](https://github.com/sase-org/sase--plans/blob/main/202609/xprompt_keyword_arg_highlighting.md)

## Description

lsp-tokens: grow the xprompt LSP semantic token legend with standard LSP token types and emit argument-structure tokens from the core spans, merged against the existing artifact, code, and glossary tokens.

## Notes

[2026-09-16T01:58:18Z · sase-11i.2] Implemented LSP semantic-token support for xprompt/directive argument spans in sase-core, verified legend append stability, nested artifact precedence, fenced-block exclusion, JSON-RPC semantic tokens, cargo fmt --check, targeted cargo tests, and PYO3_PYTHON=/home/bryan/.local/bin/python3.13 just check.

## Dependencies

- **Depends on:** [sase-11i.1](sase-11i.1.md) ✓ · ⧖ 2026-09-15
- **Blocks:** [sase-11i.3](sase-11i.3.md) ◐ · ⧖ 2026-09-15
- **Blocks:** [sase-11i.5](sase-11i.5.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11i.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11i.2/README.md) | [sase-11i.2](sase-11i.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f07bf53`](https://github.com/sase-org/sase-core/commit/f07bf53906f406fd51318068896739eaa34fcf2b) | feat(xprompt-lsp): emit argument semantic tokens | [sase-11i.2](sase-11i.2.md) | 2026-09-15 21:59:58 EDT |

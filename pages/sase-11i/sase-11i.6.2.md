# Bead: sase-11i.6.2 — Emit complete LSP names and argument coverage

[Bead Pages](../README.md) / [sase-11i.6](sase-11i.6.md) / sase-11i.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11i.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11i.land.md) · **Assignee:** `sase-11i.6.2` · **Size:** medium
**Created:** 2026-09-16 00:36:14 EDT · **Closed:** 2026-09-16 01:27:16 EDT
**Plan:** [202609/finish\_argument\_highlighting.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_argument_highlighting.md)

## Description

lsp-output: emit invocation and directive names and preserve multiline and partially overlapped argument spans.

## Notes

[2026-09-16T05:27:16Z · sase-11i.6.2] Implemented LSP name tokens, multiline semantic-token splitting, and overlap-preserving argument value tokens; verified cargo test -p sase_xprompt_lsp semantic_tokens --lib --test jsonrpc_stdio, cargo test -p sase_core editor::argument_spans::tests::emits_name_spans_for_xprompts_directives_and_aliases, Neovim glossary/xprompt/lsp_argument smoke scripts, and PYO3_PYTHON=/home/bryan/.local/bin/python3.13 just check. Also ran sase bead epic-symbols sase-11i.6.2 with no entries.

## Dependencies

- **Depends on:** [sase-11i.6.1](sase-11i.6.1.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11i.6.4](sase-11i.6.4.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11i.6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11i.6.2/README.md) | [sase-11i.6.2](sase-11i.6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6e2891d`](https://github.com/sase-org/sase-core/commit/6e2891d392b6cae2c7c65783fd5a68e8d46c824c) | feat(lsp): complete xprompt semantic token coverage | [sase-11i.6.2](sase-11i.6.2.md) | 2026-09-16 01:28:36 EDT |

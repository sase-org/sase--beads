# Bead: sase-52.5 — Phase 5: LSP And Neovim Highlighting

[Bead Pages](../README.md) / [sase-52](README.md) / sase-52.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-52.5`
**Created:** 2026-06-20 18:33:16 UTC
**Plan:** [202606/alt\_brace\_syntax.md](https://github.com/sase-org/sase--plans/blob/main/202606/alt_brace_syntax.md)

## Description

Repos: ../sase-core and ../sase-nvim. Make Neovim understand and display %{...}. sase-core: update editor directive metadata so surfaces describe %{...} and stop advertising %(...); keep canonical_directive_name('(') -> alt for compatibility only; change xprompt LSP alt snippet from %(${1:variant})$0 to a %{...} snippet; optionally add diagnostics for malformed %{...}. sase-nvim: add lua/sase/alt_highlight.lua, attach to markdown prompt files/gitcommit/sase/sase_prompt respecting allow_all_markdown, highlight %{ } | and named branch prefixes via extmarks/match groups, debounce rescans, cap scanned content, define groups SaseAltDelimiter/SaseAltSeparator/SaseAltBranchName/SaseAltError, add headless tests. Validation: cargo test -p sase_xprompt_lsp directive_snippet; headless lua tests/alt_highlight.lua; re-run tests/lsp_snippet_smoke.lua.

## Notes

Phase 5 complete (../sase-core + ../sase-nvim).

sase-core:
- editor/directive.rs: alt DirectiveMetadata now alias=None with description '...; shorthand %{A | B}', so completion/hover stop advertising %(...). canonical_directive_name('(')->alt kept for parse-compat; removed the now-dead '(' alias special-case in completion candidate matching. Added test alt_metadata_advertises_brace_shorthand.
- sase_xprompt_lsp/server.rs: alt directive snippet changed from %(${1:variant})$0 to %{${1:A} | ${2:B}\}$0 (label still %alt:... for discoverability); dropped dead '(' alias filter. Added test directive_snippet_for_alt_uses_brace_shorthand.
- Skipped optional malformed-%{...} diagnostics (design-sanctioned); rely on launch-time parser errors.

sase-nvim:
- lua/sase/alt_highlight.lua (new): line-based, depth/backtick-aware extmark highlighter mirroring core grammar. Groups SaseAltDelimiter/SaseAltSeparator/SaseAltBranchName/SaseAltError with default links. Debounced rescans + byte/line caps. Reuses sase.lsp eligibility (markdown prompt files/gitcommit/sase/sase_prompt, allow_all_markdown).
- lua/sase/init.lua: wires alt_highlight.setup via require('sase').setup({ alt_highlight = {...} }).
- tests/alt_highlight.lua (new): scan_line span placement + supports_buffer eligibility + highlight_buffer extmark gating.
- README left to Phase 7 (owns docs).

Validation (all pass): cargo fmt --check; cargo test -p sase_xprompt_lsp directive_snippet; cargo test -p sase_core editor/agent_launch; nvim headless tests/alt_highlight.lua; tests/alt_highlight + tests/lsp_config + tests/lsp_snippet_smoke (against modified LSP binary); luacheck clean. Changes left uncommitted.

## Dependencies

- **Depends on:** [sase-52.1](sase-52.1.md) ✓
- **Blocks:** [sase-52.6](sase-52.6.md) ✓
- **Blocks:** [sase-52.7](sase-52.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-52.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-52.5/README.md) | [sase-52.5](sase-52.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@0d4f6ec`](https://github.com/sase-org/sase-core/commit/0d4f6ec29645406222e82eef304c53c5b57e83a9) | feat(lsp): advertise %{A \| B} alt shorthand in directive surfaces (sase-52.5) | [sase-52.5](sase-52.5.md) | 2026-06-20 20:00:56 |

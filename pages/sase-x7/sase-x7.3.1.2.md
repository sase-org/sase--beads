# Bead: sase-x7.3.1.2 — Canonicalize the Neovim integration

[Bead Pages](../README.md) / [sase-x7.3.1](sase-x7.3.1.md) / sase-x7.3.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-x7.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.3.md) · **Assignee:** `sase-x7.3.1.2` · **Size:** medium
**Created:** 2026-09-06 09:14:53 EDT · **Closed:** 2026-09-06 10:14:26 EDT
**Plan:** [202609/canonical\_producers.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_producers.md)

## Description

editor-producers: migrate Neovim filetype, schema, catalog, reference, and fallback-completion surfaces to canonical names.

## Notes

[2026-09-06T14:14:26Z · sase-x7.3.1.2] Implemented canonical sase-nvim producer migration: ProjectSpec filetype/syntax for .sase only, canonical YAML/LSP xprompt associations, picker backend naming with old-value alias, patch-kind fixtures/docs. Verified all tests/*.lua with nvim --headless -u NONE -c "set rtp+=." -l, git diff --check, legacy producer grep, chezmoi Neovim config grep, and epic-symbols none.

## Dependencies

- **Depends on:** [sase-x7.3.1.1](sase-x7.3.1.1.md) ✓ · ⧖ 2026-09-06
- **Blocks:** [sase-x7.3.1.4](sase-x7.3.1.4.md) ◐ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.3.1.2/README.md) | [sase-x7.3.1.2](sase-x7.3.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-nvim | [`sase-nvim@84d55af`](https://github.com/sase-org/sase-nvim/commit/84d55afb8301fa464d370e490d29e6e67a6fd96d) | feat(nvim): canonicalize project specs and picker fallback | [sase-x7.3.1.2](sase-x7.3.1.2.md) | 2026-09-06 10:15:47 EDT |

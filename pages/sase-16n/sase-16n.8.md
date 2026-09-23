# Bead: sase-16n.8 — sase-nvim project tag highlighting and picker

[Bead Pages](../README.md) / [sase-16n](README.md) / sase-16n.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pl.md) · **Assignee:** `sase-16n.8` · **Size:** small
**Created:** 2026-09-22 18:48:53 EDT · **Closed:** 2026-09-22 21:27:42 EDT
**Plan:** [202609/project\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags.md)

## Description

nvim: accent highlight groups built from the server palette, a semantic-token handler for saseProjectTag, + support in the Ctrl+T picker, README, and smoke tests.

## Notes

[2026-09-23T01:27:42Z · sase-16n.8] nvim phase done in sase-nvim checkout: new project_tag_highlight.lua (SaseProjectTagAccent0-17 from server palette via on_init, Unknown/Disabled groups, saseProjectTag LspTokenUpdate handler), + token recognition in complete/_token.lua with picker routing to LSP in complete.lua, setup wiring in init.lua, README updated to tag-form completion/highlighting. Tests: new project_tag_token.lua, project_tag_highlight.lua, lsp_project_tag_highlight_smoke.lua all pass; lsp_vcs_project_smoke.lua rewritten to tag-form expansions and passes; existing unit suites (complete_backend, completion_helpers, xprompt_semantic_highlight, glossary, alt) still pass. epic-symbols clean. Note: smoke runs used SASE_XPROMPT_LSP_CMD pointing at the workspace .venv 0.34.72 server; the committed resolve chain is unchanged.

## Dependencies

- **Blocks:** [sase-16n.10](sase-16n.10.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-16n.3](sase-16n.3.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-16n.4](sase-16n.4.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.8/README.md) | [sase-16n.8](sase-16n.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.8][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.8/README.md

<!-- sase:referenced-by:end -->

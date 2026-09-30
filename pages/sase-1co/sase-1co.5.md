# Bead: sase-1co.5 — sase-nvim alternation highlighting from LSP tokens

[Bead Pages](../README.md) / [sase-1co](README.md) / sase-1co.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u1.md) · **Assignee:** `sase-1co.5` · **Size:** medium
**Created:** 2026-09-29 16:22:07 EDT · **Closed:** 2026-09-29 17:38:35 EDT
**Plan:** [202609/midword\_alternation.md](https://github.com/sase-org/sase--plans/blob/main/202609/midword_alternation.md)

## Description

nvim-lsp-highlight: in sase-nvim, replace the Lua copy of the alternation grammar with an overlay driven by LSP semantic tokens that keeps the `SaseAlt*` groups. Apply the new opener rule to `alt_edit.lua`, and update the tests and the README.

## Notes

[2026-09-29T21:38:21Z · sase-1co.5] PROPOSED FOLLOW-UP: sase lsp wrapper appears to self-recurse when SASE_XPROMPT_LSP_CMD points at "sase lsp" itself (client starts but never initializes); use a direct binary path instead

[2026-09-29T21:38:35Z · sase-1co.5] alt_highlight.lua is now an LspTokenUpdate overlay mapping alternation-modifier tokens to SaseAlt* groups (no Lua grammar copy); alt_edit.lua takes any % before { as opener, skips inline-code openers, prefers innermost span, bounds unclosed spans to their line. Verified: tests/alt_highlight.lua + tests/alt_edit.lua pass headless, new tests/lsp_alt_highlight_smoke.lua OK against fresh sase-core server (mid-word tokens, named branch, unclosed opener), full unit suite green, README updated

## Dependencies

- **Depends on:** [sase-1co.2](sase-1co.2.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1co.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.5/README.md) | [sase-1co.5](sase-1co.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-nvim | [`sase-nvim@332b7ab`](https://github.com/sase-org/sase-nvim/commit/332b7ab669e0e4dd918e5d0e5a0a1c7add75e09d) | feat(nvim): source alt-brace highlighting from LSP semantic tokens | [sase-1co.5](sase-1co.5.md) | 2026-09-29 17:40:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1co.5][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1co.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.land/README.md

<!-- sase:referenced-by:end -->

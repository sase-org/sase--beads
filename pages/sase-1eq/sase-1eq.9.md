# Bead: sase-1eq.9 — sase-nvim cutover

[Bead Pages](../README.md) / [sase-1eq](README.md) / sase-1eq.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v4.md) · **Assignee:** `sase-1eq.9` · **Size:** medium
**Created:** 2026-10-02 06:51:32 EDT · **Closed:** 2026-10-03 13:53:34 EDT
**Plan:** [202610/xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/xprompts_to_macros.md)

## Description

nvim: rename sase-nvim's Lua modules, setup keys, commands, highlight groups, Telescope extension, and LSP client name, with deprecation shims. Talk to sase macro and sase-macro-lsp first, falling back to the legacy CLI and binary names.

## Notes

[2026-10-03T17:52:40Z · sase-1eq.9] PROPOSED FOLLOW-UP: 5 nvim LSP smokes fail identically on the clean base tree from installed-server drift (venv server 0.36.4 predates smoke expectations): model_shortcut `*` trigger, project_tag palette Accent3, artifact_ref fuzzy rank, vcs_project `+s` expansion, vcs_ref ship-completion item

[2026-10-03T17:53:08Z · sase-1eq.9] PROPOSED FOLLOW-UP: `sase lsp` wrapper recurses when SASE_MACRO_LSP_CMD="sase lsp" (24 nested spawns observed; stdio server path never initializes) — consider a self-reference guard or documenting that the env must name the backend binary, not the wrapper

[2026-10-03T17:53:34Z · sase-1eq.9] nvim cutover done in repos/linked/sase-nvim: 5 Lua modules + plugin + 2 tests + fixture git-mv'd to macro names; setup keys (macro_highlight/macro_spacer), commands (:SaseMacros*), highlight groups (SaseMacroArg*), Telescope export (macros), CLIENT_NAME (sase-macro-lsp), augroups and loaded guard renamed — each with one-time-deprecation legacy shims; CLI/binary/env/schema/path/smoke resolution is new-first with legacy fallbacks marked for legacy_xprompt_syntax removal; README gains a migration section; chezmoi sase_nvim.lua confirmed untouched. Verified: 13/13 headless unit tests pass; 8/13 LSP smokes pass against venv server 0.36.4; remaining 5 smokes fail byte-identically on the clean base tree (pre-existing server drift, recorded as follow-ups). epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1eq.10](sase-1eq.10.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1eq.4](sase-1eq.4.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.9/README.md) | [sase-1eq.9](sase-1eq.9.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.9][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.9/README.md

<!-- sase:referenced-by:end -->

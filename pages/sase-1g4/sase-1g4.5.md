# Bead: sase-1g4.5 — Plugin-shared enums, sase macro types, and plugins.required

[Bead Pages](../README.md) / [sase-1g4](README.md) / sase-1g4.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0wj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wj.md) · **Assignee:** `sase-1g4.5` · **Size:** large
**Created:** 2026-10-04 18:19:35 EDT · **Closed:** 2026-10-05 14:45:13 EDT
**Plan:** [202610/macro\_named\_input\_types.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_named_input_types.md)

## Description

plugin-types: load plugin input_types.yml files in sase-core, resolve <dist>@<id> with clear missing-plugin errors, discover files with their distributions in Python and export them to the LSP, add the sase macro types command, and extend the doctor check with registry and plugins.required findings.

## Notes

[2026-10-05T18:44:38Z · sase-1g4.5--2] PROPOSED FOLLOW-UP: test_macro_docs_and_memory_avoid_xprompt_terms fails on clean base (HEAD 69b492c278 with WIP stashed) due to 11 xprompt lines in docs/images/macro-resolution-infographic.prompt.md added by sase-1eq.12.3 commit b6114d4f95; needs allowlist or prompt reword, owned outside plugin_input_types phase.

[2026-10-05T18:45:13Z · sase-1g4.5--2] plugin-types done: sase-core registry loader (schema/duplicate/normalization/quote parity, bad-type isolation) + bindings (load/resolve/catalog with round-trip); Python discovery/disconnect cache with stat invalidation + cached-diagnostic re-emit, runtime short/longform + choices-override rejection, LSP JSON env export + registry-aware catalog/diagnostics/hover/refresh; CLI sase macro types table/detail/JSON + help/completion/kind hint; doctor registry + missing-plugin + plugins.required WARN. Tests: focused 11 passed (parser_show, strings, kind, snapshot x2 incl drift, plugin_input_types 6); sase tool run check c5594cb2245d6483650ac37219110876 had 5 NEW +1 KNOWN, fixed 4 phase-caused, remaining test_macro_docs_and_memory_avoid_xprompt_terms reproduces on clean base (infographic.prompt.md from sase-1eq.12.3 b6114d4f95, PROPOSED FOLLOW-UP noted); epic-symbols clean.

[2026-10-05T19:28:58Z · sase-1g4.5--3] PROPOSED FOLLOW-UP: docs/images/macro-resolution-infographic.prompt.md carries 11 non-allowlisted xprompt lines, failing test_macro_docs_and_memory_avoid_xprompt_terms on the clean base (verified: file unmodified by this phase, all 11 findings present at HEAD). Either allowlist the prompt-source rename rows or reword them to macro spelling.

## Dependencies

- **Depends on:** [sase-1g4.4](sase-1g4.4.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.7](sase-1g4.7.md) ◐ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.5.md) | [sase-1g4.5](sase-1g4.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@af5df61`](https://github.com/sase-org/sase-core/commit/af5df614a70a02995a1dc0b9c05337b719145289) | feat(core): load plugin input\_type registries with resolution, catalog, and LSP wiring | [sase-1g4.5](sase-1g4.5.md) | 2026-10-05 15:29:56 EDT |
| sase | [`8fc4b4c`](https://github.com/sase-org/sase/commit/8fc4b4ccd65b3e39205847990076da0b9ec3152c) | feat(macro): resolve plugin-shared enum input types in runtime, LSP, CLI, and doctor | [sase-1g4.5](sase-1g4.5.md) | 2026-10-05 15:34:30 EDT |

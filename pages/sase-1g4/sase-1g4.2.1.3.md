# Bead: sase-1g4.2.1.3 — Choice diagnostics, diagnostic-driven fixes, and rich argument hover

[Bead Pages](../README.md) / [sase-1g4.2.1](sase-1g4.2.1.md) / sase-1g4.2.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1g4.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.2.md) · **Assignee:** `sase-1g4.2.1.3` · **Size:** medium
**Created:** 2026-10-05 02:19:27 EDT · **Closed:** 2026-10-05 05:50:39 EDT
**Plan:** [202610/macro\_choice\_wires\_lsp.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_choice_wires_lsp.md)

## Description

diagnostics: carry structured suggestions and edits in diagnostics, classify invalid enum arguments with the required error code, implement invocation and frontmatter quick fixes, and render shared type labels, provenance, defaults, and bounded choice tables in hover.

## Notes

[2026-10-05T09:49:42Z · sase-1g4.2.1.3] PROPOSED FOLLOW-UP: Host just check dies in _setup on sase_content_layout probe schema 6 vs expected 5 (pre-existing; identical on clean host tree).

[2026-10-05T09:49:53Z · sase-1g4.2.1.3] PROPOSED FOLLOW-UP: sase-core clippy -D warnings fails on contracts-phase 0d27dada type_complexity in editor/macro_arg_choices.rs:94/126/152 and macro_catalog/parsing.rs:651 parse_short_input_value, plus cloned_ref_to_slice_refs at macro_arg_choices.rs:373; identical on clean core HEAD.

[2026-10-05T09:50:04Z · sase-1g4.2.1.3] PROPOSED FOLLOW-UP: canonical_local_section_wins_on_helper_name_conflict fails with duplicate YAML key "macros" plus unknown `_helper` (xprompt-rename leftover on sase-1eq); local_macro_entries still iterates ["macros","macros"].

[2026-10-05T09:50:15Z · sase-1g4.2.1.3] PROPOSED FOLLOW-UP: Host surfaces still expect invalid_xprompt_arg_type for path mismatches while core publishes invalid_macro_arg_type (xprompt-rename leftover on sase-1eq).

[2026-10-05T09:50:39Z · sase-1g4.2.1.3] Diagnostics phase: closed-set args emit invalid_xprompt_arg_choice with ranked suggestions and preferred Replace-with quick fixes (positional/colon/repeatable, labels rejected, case-sensitive, non-BMP 😀#choose); frontmatter unknown-type/string→line/quote fixes; hover type-label/source/default/table-cap-12 including agent; JSON-RPC stdio edition=breif Error→preferred brief edit. Factor parse_short_input_hint tuple for clippy. epic-symbols: none leftover. Pre-existing host schema 6vs5, contracts clippy, and xprompt-rename lib leftovers recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1g4.2.1.1](sase-1g4.2.1.1.md) ✓ · ⧖ 2026-10-05
- **Depends on:** [sase-1g4.2.1.2](sase-1g4.2.1.2.md) ✓ · ⧖ 2026-10-05
- **Blocks:** [sase-1g4.2.1.5](sase-1g4.2.1.5.md) ◐ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.2.1.3/README.md) | [sase-1g4.2.1.3](sase-1g4.2.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ecd2e07`](https://github.com/sase-org/sase-core/commit/ecd2e074b4489c0c326e2137075dfd29be2bc384) | feat(lsp): classify enum diagnostics and drive diagnostic quick fixes | [sase-1g4.2.1.3](sase-1g4.2.1.3.md) | 2026-10-05 05:51:47 EDT |

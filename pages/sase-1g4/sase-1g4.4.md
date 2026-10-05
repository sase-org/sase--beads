# Bead: sase-1g4.4 — Builtin model and effort types with one routing classifier

[Bead Pages](../README.md) / [sase-1g4](README.md) / sase-1g4.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0wj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wj.md) · **Assignee:** `sase-1g4.4` · **Size:** large
**Created:** 2026-10-04 18:19:33 EDT
**Plan:** [202610/macro\_named\_input\_types.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_named_input_types.md)

## Description

model-core: register builtin effort (closed enum) and model (domain) types; add the Rust model classifier over a model validity snapshot shared by the runtime binder, sase doctor, and the LSP (via a routing block in model_catalog.json); give model arguments the %model completion menu, warnings, quick fixes, and hover in the LSP.

## Notes

[2026-10-05T12:27:37Z · sase-1g4.2.1.land] sase-1g4.2.1 landing renamed the closed-set argument diagnostic to invalid_macro_arg_choice to match the post-flip *_macro_arg* codes; emit the model warning as invalid_macro_arg_model, not the design's invalid_xprompt_arg_model.

[2026-10-05T12:58:24Z · sase-1g4.2.1.land--1] sase-1g4.2.1 landing renamed the closed-set argument diagnostic to invalid_macro_arg_choice to match the post-flip *_macro_arg* codes; emit the model warning as invalid_macro_arg_model, not the design's invalid_xprompt_arg_model.

[2026-10-05T14:19:12Z · sase-1g4.4--1] PROPOSED FOLLOW-UP: completion_context_macro_variants_pin_legacy_output is red on the untouched base tree (legacy xprompt_argument_* spellings no longer parse after the macro-spelling flip); the new MacroArgumentModel variant follows the live macro_argument_* spelling and needs no pin change once the pin is repaired.

[2026-10-05T14:23:29Z · sase-1g4.4--1] PROPOSED FOLLOW-UP: 4 more sase-core editor tests fail identically on the untouched base tree (duplicate_local_sections_are_an_error_naming_macros, builds_frontmatter_field_hover, canonical_local_section_wins_on_helper_name_conflict, macro_argument_source_accepts_old_and_new_spellings); verified via stash-compare, not caused by this phase.

[2026-10-05T14:27:28Z · sase-1g4.4--1] PROPOSED FOLLOW-UP: 6 sase_core_py binding tests and 2 sase_macro_lsp server tests fail identically on the untouched base tree (xprompt/macro rename fallout plus agent-scan/proc spelling pins); verified via stash-compare, not caused by this phase.

## Dependencies

- **Depends on:** [sase-1g4.2](sase-1g4.2.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.5](sase-1g4.5.md) ◐ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.6](sase-1g4.6.md) ◐ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.4.md) | [sase-1g4.4](sase-1g4.4.md) | 0 |

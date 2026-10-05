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

## Dependencies

- **Depends on:** [sase-1g4.2](sase-1g4.2.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.5](sase-1g4.5.md) ◐ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.6](sase-1g4.6.md) ◐ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.4/README.md) | [sase-1g4.4](sase-1g4.4.md) | 0 |

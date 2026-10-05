# Bead: sase-1g4.2 — Choices, named types, and roles on every wire; enum completion and diagnostics in the LSP

[Bead Pages](../README.md) / [sase-1g4](README.md) / sase-1g4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0wj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wj.md) · **Assignee:** `sase-1g4.2` · **Size:** large
**Created:** 2026-10-04 18:19:30 EDT · **Closed:** 2026-10-05 08:58:09 EDT
**Plan:** [202610/macro\_named\_input\_types.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_named_input_types.md)

## Description

wire-lsp: carry choices/named_type/value_role on every hint, catalog, mobile, and CLI projection; add the shared Rust choice-candidate builder and type label; give the LSP enum completion, invocation diagnostics with "Replace with" quick fixes, rich hover, and frontmatter type completion; add shared golden fixtures.

## Notes

[2026-10-05T12:58:45Z · sase-1g4.2.1.land--1] LANDING CLOSEOUT (sase-1g4.2.1 tale 202610/land_macro_choice_wires_lsp.md): phase auto-closed done when child epic sase-1g4.2.1 closed. Scope confirmed delivered by that epic: choices, named_type, value_role on every hint/catalog/mobile/CLI projection; shared Rust candidate builder (macro_argument_choice_candidates) and type label (macro_input_type_label); LSP enum completion incl. frontmatter type values; invocation diagnostics with Replace-with quick fixes; rich argument hover; shared golden fixtures. Verification: monitor nmwyhv7t2ygf / ToolRun 26b14a7f50ffc041cf3af29334cfcb6b, OVERALL_FAIL=none; only expected pre-existing sase-1eq failures remain. Epic sase-1g4 stays open for its own land agent.

## Dependencies

- **Depends on:** [sase-1g4.1](sase-1g4.1.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.3](sase-1g4.3.md) ◐ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.4](sase-1g4.4.md) ◐ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.2.md) | [sase-1g4.2](sase-1g4.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g4.2.1.1][1] | Need parent phase scope | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.2.1.1/README.md

<!-- sase:referenced-by:end -->

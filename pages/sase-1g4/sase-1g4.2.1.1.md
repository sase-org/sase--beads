# Bead: sase-1g4.2.1.1 — Resolved Rust wires, shared choice candidates, and type labels

[Bead Pages](../README.md) / [sase-1g4.2.1](sase-1g4.2.1.md) / sase-1g4.2.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1g4.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.2.md) · **Assignee:** `sase-1g4.2.1.1` · **Size:** medium
**Created:** 2026-10-05 02:19:24 EDT · **Closed:** 2026-10-05 02:57:21 EDT
**Plan:** [202610/macro\_choice\_wires\_lsp.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_choice_wires_lsp.md)

## Description

contracts: preserve resolved metadata through Rust catalog/editor/mobile wires, implement and bind the shared candidate builder and type label, classify argument contexts using roles and choices, and establish the parser-driven golden corpus and additive wire compatibility tests.

## Notes

[2026-10-05T06:56:37Z · sase-1g4.2.1.1] PROPOSED FOLLOW-UP: Repair 14 pre-existing sase-core lib failures from xprompt->macro rename (flip commit 0279de6b) — agent_launch legacy-key, agent_stats legacy spellings (3), runner_occupancy, content_layout canonical dirs, diagnostics canonical_local_section (duplicate macros key from ["macros","macros"] loop), frontmatter duplicate_local_sections, hover frontmatter field, wire legacy-output pins (2), macro_catalog canonical insertions (xprompt vs macro kind), procs legacy spellings, query profile digest — all reproduce identically on clean base (4412 passed/14 failed base vs 4416 passed/14 failed with contracts; +4 new golden tests pass)

[2026-10-05T06:57:21Z · sase-1g4.2.1.1] Contracts land: named_type/value_role on MacroInputHint/MobileMacroInputWire/CatalogInput with short/long/local parsing preserved; shared macro_argument_choice_candidates (prefix-then-fuzzy, bool synth, repeatable exclusion keeping active, comma/plus quoting) and macro_input_type_label (union<=4 else named/enum count; bool stays bool) bound in editor-completion with old-hint compat; trigger contexts classified by role/choices/bool/path with parser top-level comma/equals spans (empty, mid-value, quoted, named/positional/colon, repeatable tail); golden corpus macro_arg_choice_completion.json (15 cases, UTF-8 bytes + UTF-16 non-BMP) drives detection/builder/applied-edit binder agreement including pr:ready->name; gateway mobile contract additive named_type/value_role; sase validate probes conditional + docs. Verified: sase_core macro_arg_choices 4 pass, trigger_context 6 pass, sase_core_py choice 1 pass, sase probe direct 3 pass, full lib 4416 pass/14 fail identical to clean base 4412/14 (pre-existing flip-commit, filed as follow-up); epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1g4.2.1.2](sase-1g4.2.1.2.md) ◐ · ⧖ 2026-10-05
- **Blocks:** [sase-1g4.2.1.3](sase-1g4.2.1.3.md) ◐ · ⧖ 2026-10-05
- **Blocks:** [sase-1g4.2.1.4](sase-1g4.2.1.4.md) ✓ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.2.1.1/README.md) | [sase-1g4.2.1.1](sase-1g4.2.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0d27dad`](https://github.com/sase-org/sase-core/commit/0d27dada58d711d4bb71b179a6624c1bff882b63) | feat(macros): carry resolved choice metadata and shared candidates | [sase-1g4.2.1.1](sase-1g4.2.1.1.md) | 2026-10-05 02:58:52 EDT |
| sase | [`4fd4039`](https://github.com/sase-org/sase/commit/4fd4039a5acd2a4db3da82d1c6230ef244e27096) | feat(macros): probe shared choice candidates and type labels | [sase-1g4.2.1.1](sase-1g4.2.1.1.md) | 2026-10-05 03:03:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g4.2.1.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.2.1.1/README.md

<!-- sase:referenced-by:end -->

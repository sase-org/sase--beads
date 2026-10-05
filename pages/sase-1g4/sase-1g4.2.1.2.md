# Bead: sase-1g4.2.1.2 — Enum completion and frontmatter type completion in the LSP

[Bead Pages](../README.md) / [sase-1g4.2.1](sase-1g4.2.1.md) / sase-1g4.2.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1g4.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.2.md) · **Assignee:** `sase-1g4.2.1.2` · **Size:** medium
**Created:** 2026-10-05 02:19:25 EDT · **Closed:** 2026-10-05 04:21:17 EDT
**Plan:** [202610/macro\_choice\_wires\_lsp.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_choice_wires_lsp.md)

## Description

completion: consume shared choice candidates in standard LSP responses, replace the bool-only path, implement catalog-backed frontmatter type completion, and verify full-value text edits through JSON-RPC.

## Notes

[2026-10-05T08:20:39Z · sase-1g4.2.1.2] PROPOSED FOLLOW-UP: Refresh the pinned-core setup probes — sase tool run check 0e797bea2519fd5099f6d7d69cb8bcd2 failed in _setup because sase_content_layout reports schema 6 while tools/validate_sase_core_rs expects 5; identical clean-core mismatch recorded in sase-1g4.1 note #1 and sase-1g4.2.1.4 note #1 (no standalone task bead in search).

[2026-10-05T08:20:50Z · sase-1g4.2.1.2] PROPOSED FOLLOW-UP: Repair sase-core clippy -D warnings on contracts-phase HEAD 0d27dada (sase-1g4.2.1.1) — type_complexity in editor/macro_arg_choices.rs, editor/diagnostics.rs, macro_catalog/parsing.rs and cloned_ref_to_slice_refs in the choices golden test; sase tool run check 09b375036b38bcda8530442725d17824 failed at clippy before tests; files are not in this phase dirty set. Cite also sase-1g4.2.1.1 note #1 for the 14 xprompt-rename lib failures clippy blocked from re-running.

[2026-10-05T08:21:17Z · sase-1g4.2.1.2] Verified enum/bool LSP completion via shared macro_argument_choice_candidates: ENUM_MEMBER items, filterText=value, sortText=index, full-value textEdit (unclosed mid-value #deploy(env=st|aging) replaces 12..19 after paren_arg_context body_end=text.len()), quoted punctuation insertion, display-only default badge, no preselect. Colon #deploy: offers enum values; #deploy( still offers env=. Frontmatter advertised types (word/enum/agent present, string absent) on type: and shortform env: slots, whole-token replace, no body/unrelated YAML. JSON-RPC stdio covers trigger characters plus choice and frontmatter type completion on eligible sase_prompt_ URI. Tests: sase_core frontmatter input_type_completion (6), sase_macro_lsp choice (11 lib + 1 JSON-RPC), golden_detection_builder_and_applied_edits. Clippy --no-deps -p sase_macro_lsp and just fast -p sase_core -p sase_macro_lsp green. epic-symbols empty. Host sase check blocked by known content_layout schema 6 vs probe 5; sase-core just check blocked by contracts-phase clippy on HEAD 0d27dada — both filed as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1g4.2.1.1](sase-1g4.2.1.1.md) ✓ · ⧖ 2026-10-05
- **Blocks:** [sase-1g4.2.1.3](sase-1g4.2.1.3.md) ✓ · ⧖ 2026-10-05
- **Blocks:** [sase-1g4.2.1.5](sase-1g4.2.1.5.md) ✓ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.2.1.2/README.md) | [sase-1g4.2.1.2](sase-1g4.2.1.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@57fee30`](https://github.com/sase-org/sase-core/commit/57fee3065a18e2ec2af4845b590040c77deab535) | feat(lsp): complete enum and frontmatter type values in the macro LSP | [sase-1g4.2.1.2](sase-1g4.2.1.2.md) | 2026-10-05 04:22:32 EDT |
| sase | [`a6df140`](https://github.com/sase-org/sase/commit/a6df140bcced9f6b1ced1154408e516fcdedb5ea) | docs(editor): document enum and frontmatter type completion in the LSP | [sase-1g4.2.1.2](sase-1g4.2.1.2.md) | 2026-10-05 04:27:05 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g4.2.1.2][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1g4.2.1.3][2] | Need completion phase handoff | 1 |
| read-by | [agent:sase-1g4.2.1.5--1][3] | Need dependency handoff notes for parity verification | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.2.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.2.1.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.2.1.5.md

<!-- sase:referenced-by:end -->

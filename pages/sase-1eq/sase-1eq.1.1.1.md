# Bead: sase-1eq.1.1.1 — Rename catalog and editor internals with pinned legacy output

[Bead Pages](../README.md) / [sase-1eq.1.1](sase-1eq.1.1.md) / sase-1eq.1.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.1.f0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.f0.md) · **Assignee:** `sase-1eq.1.1.1` · **Size:** medium
**Created:** 2026-10-02 07:55:47 EDT · **Closed:** 2026-10-02 08:34:48 EDT
**Plan:** [202610/finish\_core\_macro\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_core_macro_expand.md)

## Description

catalog-editor-names: Complete catalog/editor/content-layout internal identifier renames, update Rust consumers through owning-module imports, preserve all existing serialized values and diagnostics, and register the three macro editor/skill binding aliases. Follow the catalog-editor-names section and shared compatibility rules.

## Notes

[2026-10-02T12:34:25Z · sase-1eq.1.1.1] catalog-editor-names evidence: sase-core 015ce7f clean base; 46 files changed (macro_catalog, content_layout types, editor wires/completion/jinja, py editor_completion, lsp consumers). Renamed CatalogXprompt->CatalogMacro, XpromptCatalog*->MacroCatalog*, XpromptSkillDefinition*->MacroSkillDefinition*, XpromptSourceWire->MacroSourceWire, MemoryXprompt*->MemoryMacro*, XpromptArgument*/Assist/InputHint/CallNameSpan->Macro* (Source::Macro pinned serde rename=xprompt alias=macro), CompletionContextKind 5 arg variants pinned to legacy output, resolve/load/build/extract/parse helpers renamed, root lib.rs xprompt re-exports + prelude core_* aliases removed (owning-module imports), 3 py aliases added on same impls (resolve_macro_skill_definition, macro_skill_definition_wire_schema_version, macro_argument_spans) with legacy names+exception text kept. Residual 785 hit-lines classified: emission pins (diagnostics, locator strings, xprompt_name field, schema v1), deferred to catalog-sources (xprompts/macro_sources fields, SASE_XPROMPT_*, option keys), authored-inputs (xprompts: keys, frontmatter/directive markers), runtime-wire-names (stats/proc/launch wires), lsp-inputs (XpromptLspServer, commands). No clean-base failures seen.

[2026-10-02T12:34:48Z · sase-1eq.1.1.1] catalog-editor-names done: sase tool run check succeeded (run 6a01696c02cbdc197134729df36f77ed) on sase-core 015ce7f base; targeted editor 411/content_layout 14/py-editor_completion 26/macro_catalog 32 pass incl 3 new parity tests (serde old/new alias pins, py alias agreement, schema v1); 3 macro py aliases registered on same impls with legacy output byte-identical; root/prelude exports removed per plan; no epic-symbols; no clean-base failures

## Dependencies

- **Blocks:** [sase-1eq.1.1.2](sase-1eq.1.1.2.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.1.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.1.1.1/README.md) | [sase-1eq.1.1.1](sase-1eq.1.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c4444ab`](https://github.com/sase-org/sase-core/commit/c4444abbf25508844d040356d4b423329e0f0dbc) | feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output | [sase-1eq.1.1.1](sase-1eq.1.1.1.md) | 2026-10-02 08:36:12 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.1.1.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.1.1.1/README.md

<!-- sase:referenced-by:end -->

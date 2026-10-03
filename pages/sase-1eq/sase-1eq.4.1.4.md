# Bead: sase-1eq.4.1.4 — Macro CLI, completion, and retirement diagnostics

[Bead Pages](../README.md) / [sase-1eq.4.1](sase-1eq.4.1.md) / sase-1eq.4.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.md) · **Assignee:** `sase-1eq.4.1.4` · **Size:** medium
**Created:** 2026-10-03 06:00:02 EDT · **Closed:** 2026-10-03 10:28:35 EDT
**Plan:** [202610/macro\_syntax\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_syntax_cutover.md)

## Description

cli-doctor: publish canonical macro commands and JSON, hide flag-gated old aliases, repair schema path targets, refresh shell completion, and report every retired authored surface in either flag state.

## Notes

[2026-10-03T14:25:15Z · sase-1eq.4.1.4] PROPOSED FOLLOW-UP: tests/completion/test_candidates_providers.py::test_snippet_candidates_use_rust_loader fails identically on the clean base tree (fake 2-arg load_editor_snippet_catalog loader vs 3-arg call site); pre-existing, unrelated to cli-doctor changes

[2026-10-03T14:25:28Z · sase-1eq.4.1.4] PROPOSED FOLLOW-UP: snippet loader test fails on clean base tree (pre-existing, unrelated to cli-doctor)

[2026-10-03T14:27:31Z · sase-1eq.4.1.4] PROPOSED FOLLOW-UP: tests/doctor/test_checks_beads.py::test_project_beads_skips_when_store_is_absent fails identically on the clean base tree (expects SKIP, gets OK; workspace beads store present); pre-existing, unrelated to cli-doctor

[2026-10-03T14:28:35Z · sase-1eq.4.1.4] cli-doctor done: sase macro canonical (xprompt hidden alias, flag-gated retirement error when off; dest macro_subcommand; full+narrow parsers; bare defaults to list); sase path macros-{dir,schema,collection-schema} canonical with gated aliases; new macros-collection.schema.json packaged (old target pointed at missing xprompts.schema.json); macro-catalog canonical helper in mobile+editor bridges; ValueKind.MACRO=macro with legacy kind shim; CLI JSON type/kind macro (list/show/catalog); doctor ids config.model_macros/config.macro_definitions/config.macro_directives/tools.macro_lsp plus new config.retired_xprompt_names reporting raw layers/dirs/frontmatter/env/plugin-groups in both states; cli_spec.json regenerated with zero xprompt entries; LSP/prompt-save/project/run/snippet/root help canonical. Verified: 705 passed across affected suites; 2 failures reproduce identically on clean base and are recorded as PROPOSED FOLLOW-UP notes (snippet loader 2-vs-3-arg, beads SKIP-vs-OK). epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1eq.4.1.3](sase-1eq.4.1.3.md) ✓ · ⧖ 2026-10-03
- **Blocks:** [sase-1eq.4.1.5](sase-1eq.4.1.5.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.4.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.4.1.4/README.md) | [sase-1eq.4.1.4](sase-1eq.4.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4f90695`](https://github.com/sase-org/sase/commit/4f90695659a6eaef0cc86e1fc8656e8a1b6a9c34) | feat!: publish canonical macro CLI, completion, and retirement diagnostics | [sase-1eq.4.1.4](sase-1eq.4.1.4.md) | 2026-10-03 10:30:08 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.4.1.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.4.1.4/README.md

<!-- sase:referenced-by:end -->

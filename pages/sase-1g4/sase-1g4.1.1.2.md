# Bead: sase-1g4.1.1.2 — Route Rust parsers and frontmatter diagnostics through the catalog

[Bead Pages](../README.md) / [sase-1g4.1.1](sase-1g4.1.1.md) / sase-1g4.1.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1g4.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.1.md) · **Assignee:** `sase-1g4.1.1.2` · **Size:** medium
**Created:** 2026-10-04 18:33:17 EDT · **Closed:** 2026-10-04 21:19:05 EDT
**Plan:** [202610/macro\_input\_type\_vocab.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_input_type_vocab.md)

## Description

rewire: delete the duplicate Rust type tables, project the frontmatter schema from the catalog, align the path rule, and emit the strict frontmatter diagnostics.

## Notes

[2026-10-05T01:18:15Z · sase-1g4.1.1.2--1] PROPOSED FOLLOW-UP: Triage the intermittent ACE TUI prompt catalog failure — phase ToolRun 41e2b498627d11d472bdb7fa6de44245 and clean-base ToolRun a27322131f1298a19ca910e8deb6e434 both failed tests/ace/tui/test_prompt_catalog.py::test_prompt_source_token_changes_for_project_file. The clean-base run also had two other KNOWN failures absent from the phase run; the phase run had five other failures absent from clean base. Rerun ToolRun 9d51bee89c535b89f3518e1bd9352397 passed those five and still classified the shared prompt catalog failure as KNOWN. No regression was traced to the Rust input-type changes.

[2026-10-05T01:19:05Z · sase-1g4.1.1.2--1] Restored the phase changes from the temporary clean-base stash and reset sase-core-revision.txt to 2838c7eb181521c81e16a29c293f52bfd10d6d3e. Reviewed both repository diffs and passed git diff --check. Clean-base ToolRun a27322131f1298a19ca910e8deb6e434 had three KNOWN test failures; phase ToolRun 41e2b498627d11d472bdb7fa6de44245 shared only the prompt catalog failure. Rerun ToolRun 9d51bee89c535b89f3518e1bd9352397 passed the other five prior failures and kept the prompt catalog failure KNOWN. The linked core compiled; epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-1g4.1.1.1](sase-1g4.1.1.1.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.1.1.4](sase-1g4.1.1.4.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.1.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.1.1.2.md) | [sase-1g4.1.1.2](sase-1g4.1.1.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@048b649`](https://github.com/sase-org/sase-core/commit/048b6490a91de0c1567c4d461a69dd7219fe373c) | feat(editor): route macro input validation through shared catalog | [sase-1g4.1.1.2](sase-1g4.1.1.2.md) | 2026-10-04 21:20:22 EDT |
| sase | [`25cc3c4`](https://github.com/sase-org/sase/commit/25cc3c475d278b652c9d06e182c101efeeabf600) | chore(core): restore phase revision pin after clean-base check | [sase-1g4.1.1.2](sase-1g4.1.1.2.md) | 2026-10-04 21:24:41 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g4.1.1.2--1][1] | Need the phase scope, design file, and closure criteria | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.1.1.2.md

<!-- sase:referenced-by:end -->

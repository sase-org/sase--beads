# Bead: sase-1le.11 — How SASE works plus the agents, work-units, and landing concepts

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.11` · **Size:** medium
**Created:** 2026-10-15 18:11:12 EDT · **Closed:** 2026-10-15 22:08:22 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

concepts-model: write concepts/index.md (one diagram, seven nouns) plus agents, work-units, and landing concept hubs, and move architecture.md's internals to Contribute.

## Notes

[2026-10-16T02:07:57Z · sase-1le.11] PROPOSED FOLLOW-UP: Make generated Markdown outputs format-stable — the clean-worktree baseline check failure was at fmt-docs-check because render_glossary and render_design_decisions differ from checked-in generated pages; after rendering, Prettier reports the same pages, so align renderer output and the Markdown format gate. Search found no task bead for this; related generator work is closed phase sase-1le.8.

[2026-10-16T02:08:22Z · sase-1le.11] Added the four concepts pages, moved Architecture to Contribute with the old URL redirect, and updated the nav and homepage links. just docs-check passed with all 204 URLs; git diff --check passed; epic-symbols found no entries. sase tool run check is blocked by the pre-existing generated-doc drift recorded in the proposed follow-up note.

## Dependencies

- **Blocks:** [sase-1le.12](sase-1le.12.md) ✓ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.13](sase-1le.13.md) ◐ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.8](sase-1le.8.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.11/README.md) | [sase-1le.11](sase-1le.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ecaad7f`](https://github.com/sase-org/sase/commit/ecaad7fed830cefdac2ab1778e4e9f38acf9fcb7) | docs(sase.sh): add concepts and move architecture page | [sase-1le.11](sase-1le.11.md) | 2026-10-15 22:09:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.12][1] | Confirm whether its recorded generated-docs check failure matches this phase's baseline failure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.12/README.md

<!-- sase:referenced-by:end -->

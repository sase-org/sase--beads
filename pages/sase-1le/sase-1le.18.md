# Bead: sase-1le.18 — Generated TUI keymap, directive, and macro discovery-order references

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.18

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.18` · **Size:** medium
**Created:** 2026-10-15 18:11:14 EDT · **Closed:** 2026-10-16 07:30:00 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

keymap-directives: generate the TUI keymap tables, the directive catalog, and macro discovery order, deleting the hand-written rows in ace.md and macros.md (fixes sase-1la).

## Notes

[2026-10-16T11:29:09Z · sase-1le.18] PROPOSED FOLLOW-UP: Repair the renderer/Prettier drift in generated glossary outputs — current ToolRun c57f7fd8c9b2c13e4673233c7576015c failed at fmt-docs-check on docs/_includes/abbreviations.md, docs/reference/glossary.md, and docs/reference/design-decisions.md; the same clean-base drift is already recorded in sase-1le.19 note #1 and parent sase-1le note #4 (baseline ToolRuns 51e399dd01efffd2d78fe7ca73947fe8 and bdc66a3335d97d6fdfd620af1b4bd911 at 30c3500495), with renderer ownership in sase-1le.8. No separate task bead was found.

[2026-10-16T11:30:00Z · sase-1le.18] Generated TUI keymap, directive, and macro discovery references from their source contracts; added Reference nav and indexes, and removed duplicate hand-maintained keybinding/directive/discovery rows. Verified Prettier, Ruff, generated-doc checks, and git diff --check. `sase tool run check` stops at the known clean-base fmt-docs-check renderer/Prettier drift, recorded in the phase follow-up note.

## Dependencies

- **Depends on:** [sase-1le.14](sase-1le.14.md) ✓ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.20](sase-1le.20.md) ◐ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.8](sase-1le.8.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.18](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.18/README.md) | [sase-1le.18](sase-1le.18.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b94cffe`](https://github.com/sase-org/sase/commit/b94cffe0d3a506805def63d8f60e1c145909b82f) | feat(docs): generate TUI and macro reference catalogs | [sase-1le.18](sase-1le.18.md) | 2026-10-16 07:31:12 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.18][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1lh.5][2] | byte check closed compact | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.18/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.5/README.md

<!-- sase:referenced-by:end -->

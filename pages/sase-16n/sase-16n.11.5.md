# Bead: sase-16n.11.5 — sase-nvim picker fallback, palette overrides, and dim sigil

[Bead Pages](../README.md) / [sase-16n.11](sase-16n.11.md) / sase-16n.11.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16n.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16n.land.md) · **Assignee:** `sase-16n.11.5` · **Size:** small
**Created:** 2026-09-23 08:51:51 EDT · **Closed:** 2026-09-23 09:33:19 EDT
**Plan:** [202609/project\_tags\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags_landing_gaps.md)

## Description

nvim-fixes: the Ctrl+T +query picker works without native LSP completion; palette application keeps user overrides; the + sigil renders in dim accent; disabled tags use the new server modifier; README and tests match.

## Notes

[2026-09-23T13:33:19Z · sase-16n.11.5] nvim-fixes done in sase-nvim: +query picker fallback via sase project list --json (new complete/project_tag.lua, wired into complete.lua), palette refresh preserves user/colorscheme overrides (force removed in highlight + lsp on_init), SaseProjectTagSigil0-17 dim-accent groups mapped for sigil tokens with disabled->Disabled kept. README updated (fallback, sigil table, smoke steps). All 12 headless unit suites pass incl. new project_tag_picker.lua; live fetch verified against real sase CLI (3 tags, filter OK).

## Dependencies

- **Depends on:** [sase-16n.11.1](sase-16n.11.1.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16n.11.6](sase-16n.11.6.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.11.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.5/README.md) | [sase-16n.11.5](sase-16n.11.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-nvim | [`sase-nvim@dac30c9`](https://github.com/sase-org/sase-nvim/commit/dac30c925e16266d6f8954582de69ee7053d85d4) | feat(nvim): project-tag picker fallback, palette overrides, dim sigil | [sase-16n.11.5](sase-16n.11.5.md) | 2026-09-23 09:34:46 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.11.5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.5/README.md

<!-- sase:referenced-by:end -->

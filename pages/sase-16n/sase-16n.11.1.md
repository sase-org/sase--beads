# Bead: sase-16n.11.1 — sase-core accept parity, target wire fields, and LSP tag fixes

[Bead Pages](../README.md) / [sase-16n.11](sase-16n.11.md) / sase-16n.11.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16n.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16n.land.md) · **Assignee:** `sase-16n.11.1` · **Size:** medium
**Created:** 2026-09-23 08:51:46 EDT · **Closed:** 2026-09-23 09:18:00 EDT
**Plan:** [202609/project\_tags\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags_landing_gaps.md)

## Description

core-fixes: accept removes every workspace target the Python one-target guard counts; LSP accept uses all tag targets; ProjectTagTargetWire gains state and workspace_dir; LSP gains disabled diagnostics/modifier and a richer hover; rewrite-to-tag emits only valid tags; suggestions are deduped; collision warnings skip siblings and flag key case variants; the dead catalog wire is used or removed.

## Notes

[2026-09-23T13:18:00Z · sase-16n.11.1] sase-core core-fixes done: accept matches Python embedded-tag guard (mid-line refs removed, empty workflow names match nothing) with new vectors; LSP accept deletions use catalog project_tags (disabled/home parity) via build_vcs_project_completion_candidates_with_targets; ProjectTagTargetWire gains serde-default state/workspace_dir with round-trip tests; disabled targets get disabled diagnostic+token modifier and state/workspace shown in hover+completion docs (v5 with/without-field catalog tests); rewrite-to-tag fires only for D1-standalone results with negative tests; suggestions dedupe fully; collision warnings exclude siblings, flag case-variant directory keys and Home keys, with casefold-difference comment and tests; LSP catalog loads through VcsProjectCatalogWire (per-field fallback preserved); scan.rs directive/frontmatter left as-is (not a mechanical swap). sase tool run check green.

## Dependencies

- **Blocks:** [sase-16n.11.2](sase-16n.11.2.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16n.11.5](sase-16n.11.5.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16n.11.6](sase-16n.11.6.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.11.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.1/README.md) | [sase-16n.11.1](sase-16n.11.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4300166`](https://github.com/sase-org/sase-core/commit/430016645d10590c75bff39fdbfc62cc89177fcd) | fix(core): project-tag core fixes for bead sase-16n.11.1 | [sase-16n.11.1](sase-16n.11.1.md) | 2026-09-23 09:19:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.11.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.1/README.md

<!-- sase:referenced-by:end -->

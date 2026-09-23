# Bead: sase-16n.11.3 — CLI and cold-TUI tag rendering, pager, MRU label, and red tests

[Bead Pages](../README.md) / [sase-16n.11](sase-16n.11.md) / sase-16n.11.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16n.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16n.land.md) · **Assignee:** `sase-16n.11.3` · **Size:** medium
**Created:** 2026-09-23 08:51:48 EDT · **Closed:** 2026-09-23 11:08:54 EDT
**Plan:** [202609/project\_tags\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags_landing_gaps.md)

## Description

display-fixes: fix the two red prompt-history label tests; CLI surfaces load the catalog so they tagify; the TUI warms the catalog at startup, refreshes cold renders, and re-highlights the editor; the metadata pager keeps Markdown highlighting around tags; MRU labels read the tag; clan triage tags are accent-colored.

## Notes

[2026-09-23T15:07:54Z · sase-16n.11.3] PROPOSED FOLLOW-UP: tests/test_vcs_xprompt_mru_pruning.py::test_load_launchable_prunes_provider_mismatched_prefix fails on clean HEAD (verified via isolated worktree) — pre-existing MRU pruning failure unrelated to display-fixes

[2026-09-23T15:08:54Z · sase-16n.11.3] display-fixes done: red prompt-history preview tests assert Text.plain plus a warm-catalog tag-style test; CLI show/list/search/xprompt-show warm the tag catalog via ensure_project_tag_catalog; app warms catalog off-thread at startup and repaints cold surfaces on ProjectTagCatalogWarmed (coalesced per signature); prompt editor re-highlights when the catalog worker lands; pager emits PROJECT_TAG spans from the Markdown pass so Markdown+tag highlighting coexist (body stays plain); MRU bar labels resolve +tag prefixes via mru_prefix_project_name; clan triage lines overlay tag accents. check: only symvision ExpandedLaunchSegments fails (known master-red, sase-16u); related suites green (297 passed; one pruning failure proven pre-existing on clean HEAD and filed as follow-up note)

## Dependencies

- **Depends on:** [sase-16n.11.2](sase-16n.11.2.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16n.11.4](sase-16n.11.4.md) ◐ · ⧖ 2026-09-23
- **Blocks:** [sase-16n.11.6](sase-16n.11.6.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.11.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.3/README.md) | [sase-16n.11.3](sase-16n.11.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b924b03`](https://github.com/sase-org/sase/commit/b924b03508978a7f28e50bd517ecca58e499a846) | feat(project-tags): CLI and cold-TUI tag rendering, pager, MRU label, and red tests | [sase-16n.11.3](sase-16n.11.3.md) | 2026-09-23 11:12:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.11.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.3/README.md

<!-- sase:referenced-by:end -->

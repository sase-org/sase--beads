# Bead: sase-1vt.1 — Published-ID collision rule in the sase-core stream merge

[Bead Pages](../README.md) / [sase-1vt](README.md) / sase-1vt.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1hj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1hj.md) · **Assignee:** `sase-1vt.1` · **Size:** medium
**Created:** 2026-11-27 15:24:24 EST · **Closed:** 2026-11-27 16:47:13 EST
**Plan:** [202611/resilient\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202611/resilient_epic_launch.md)

## Description

merge: replace the raw issue_created count in the Rust three-way stream merge with a rule that relocates any unpublished creation of a published ID and accepts create/remove/create history, plus a Python resolver regression for the incident's stream shape.

## Notes

[2026-11-27T21:47:13Z · sase-1vt.1] Implemented published-ID incarnation collision relocation in the Rust three-way stream merge, preserving older Ours-incarnation events and allowing valid create/remove/create histories; added Rust merge scenarios and Python real-rebase resolver regression. Verified focused Rust tests (17 passed), focused Python regression (1 passed), linked sase-core full check, and root sase full check (including escalated full pytest); epic-symbol audit is clear.

## Dependencies

- **Blocks:** [sase-1vt.5](sase-1vt.5.md) ✓ · ⧖ 2026-11-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vt.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vt.1/README.md) | [sase-1vt.1](sase-1vt.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7e857ed`](https://github.com/sase-org/sase-core/commit/7e857eddded8203f05a42b405f909dc3a5903e92) | fix(bead-merge): relocate published-id reincarnations | [sase-1vt.1](sase-1vt.1.md) | 2026-11-27 16:48:26 EST |
| sase | [`51fc0d8`](https://github.com/sase-org/sase/commit/51fc0d8cb2a8488c792c2a88df2aa127ee45157c) | fix(bead): relocate reincarnated issue creation conflicts | [sase-1vt.1](sase-1vt.1.md) | 2026-11-27 16:49:37 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vt.1][1] | Need the phase scope, design file, notes, and prior work state before completing this assigned phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vt.1/README.md

<!-- sase:referenced-by:end -->

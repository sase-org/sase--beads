# Bead: sase-16n.2 — Case-insensitive project name uniqueness across VCS types

[Bead Pages](../README.md) / [sase-16n](README.md) / sase-16n.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pl.md) · **Assignee:** `sase-16n.2` · **Size:** small
**Created:** 2026-09-22 18:48:46 EDT · **Closed:** 2026-09-22 19:49:53 EDT
**Plan:** [202609/project\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags.md)

## Description

unique-names: make every write-time project ref check case-insensitive and reserve home. Widen doctor project.name_collisions to every key/name/alias conflict, and mirror the rule in sase-core collision warnings and sase-github name allocation. Then verify this machine has no collisions.

## Notes

[2026-09-22T23:49:21Z · sase-16n.2] PROPOSED FOLLOW-UP: Repair pre-existing whole-repo red unrelated to unique-names — symvision flags delete_paths_in_background in _linked_repo_workspaces.py and test_artifact_directory_operation_sites_are_reviewed fails on unreviewed sites in _linked_repo_workspaces.py/_utils_checkout.py (both fail on clean tree)

[2026-09-22T23:49:53Z · sase-16n.2] unique-names done: casefolded write-time checks (alias map, conflicts, allocate, find owner with home reserved for case-variants) in sase; widened doctor name_collisions to all key/name/alias conflicts with alias-remove/rename next steps; casefolded sase-core collision warnings and sase-github canonical allocation. Verified: 37 alias+doctor tests, 58 bare-git/name/display tests, 103 github plugin tests (new case tests fail pre-fix), sase-core project_spec 31 pass + full sase-core check gate green, widened doctor OK with 0 collisions on this machine, scoped lane 45222 passed (1 pre-existing audit failure + symvision red both reproduce on clean tree, noted as follow-up)

## Dependencies

- **Blocks:** [sase-16n.10](sase-16n.10.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16n.3](sase-16n.3.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.2/README.md) | [sase-16n.2](sase-16n.2.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dc08f7b`](https://github.com/sase-org/sase/commit/dc08f7b21c31dd51853184a8607ed40c598beded) | feat(projects): enforce case-insensitive project name uniqueness | [sase-16n.2](sase-16n.2.md) | 2026-09-22 19:51:43 EDT |
| sase-core | [`sase-core@3120739`](https://github.com/sase-org/sase-core/commit/3120739433fb6c4d4abef462f15a97de8612fa71) | feat(projects): casefold project ref collision warnings and reserve home | [sase-16n.2](sase-16n.2.md) | 2026-09-22 19:54:53 EDT |
| sase-github | [`sase-github@fd5b7bd`](https://github.com/sase-org/sase-github/commit/fd5b7bde2ac2e0785640df172e7e321275df406b) | feat(projects): allocate canonical names case-insensitively | [sase-16n.2](sase-16n.2.md) | 2026-09-22 19:58:09 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.2/README.md

<!-- sase:referenced-by:end -->

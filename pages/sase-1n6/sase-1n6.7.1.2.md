# Bead: sase-1n6.7.1.2 — Read release trains and publication evidence

[Bead Pages](../README.md) / [sase-1n6.7.1](sase-1n6.7.1.md) / sase-1n6.7.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1n6.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.7.md) · **Assignee:** `sase-1n6.7.1.2` · **Size:** medium
**Created:** 2026-10-19 19:56:23 EDT · **Closed:** 2026-10-19 23:25:42 EDT
**Plan:** [202610/release\_steward\_observe.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_steward_observe.md)

## Description

train-facts: read PyPI, tags, draft releases, manifests, release PR checks, and workflow history; reuse the candidate evaluator and expose a reusable read-only reader.

## Notes

[2026-10-20T02:15:42Z · sase-1n6.7.1.2] PROPOSED FOLLOW-UP: Extend Rust active-train policy to stop initial or resumed release dispatch when retained distribution assets are missing, even if the evaluator is publishable; current policy gates retained_asset_missing only on red-verdict handling.

[2026-10-20T03:25:42Z · sase-1n6.7.1.2--2] Implemented the reusable read-only release facts reader and bounded GitHub/PyPI transports, with candidate evaluator binding and tests kept inside the existing 81-entry contract set. Verified with  (pass); epic-symbol check found no leftovers. Preserved the existing Rust active-train policy follow-up.

[2026-10-20T03:25:56Z · sase-1n6.7.1.2--2] Completion verification clarification: sase tool run check 98ab7c45a7bd3a7f7f28a6efc8343b48 passed after the contract tests were consolidated into the existing 81-entry set.

## Dependencies

- **Depends on:** [sase-1n6.7.1.1](sase-1n6.7.1.1.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.7.1.3](sase-1n6.7.1.3.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.7.1.4](sase-1n6.7.1.4.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.7.1.5](sase-1n6.7.1.5.md) ✓ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.7.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.7.1.2.md) | [sase-1n6.7.1.2](sase-1n6.7.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`23cccbc`](https://github.com/sase-org/sase/commit/23cccbc969ed14f970ac509ccedfd5358f7a93d8) | feat(release): add read-only release facts reader | [sase-1n6.7.1.2](sase-1n6.7.1.2.md) | 2026-10-19 23:27:01 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n6.7.1.2--2][1] | Need the phase scope, design file, and existing work notes before finishing | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.7.1.2.md

<!-- sase:referenced-by:end -->

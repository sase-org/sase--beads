# Bead: sase-1my.3 — release-dependency-floor check on plugin release PRs

[Bead Pages](../README.md) / [sase-1my](README.md) / sase-1my.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11s](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11s.md) · **Assignee:** `sase-1my.3` · **Size:** medium
**Created:** 2026-10-19 10:16:27 EDT · **Closed:** 2026-10-19 11:52:06 EDT
**Plan:** [202610/e1\_installable\_family.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_installable_family.md)

## Description

floor-check: add a sibling-floor satisfiability and joint-resolve check, wire it into each plugin's release PRs so it is never skipped, and rerun it on a schedule so it clears once the sibling publishes.

## Notes

[2026-10-19T15:52:06Z · sase-1my.3] Shared floor check lives in sase tools/check_release_dependency_floor plus reusable .github/workflows/release-dependency-floor.yml; sase-github, sase-telegram, and sase-research-artifacts call it at @master. Fixture tests cover unpublished/yanked/prerelease floors, joint conflict, PyPI errors, non-family ignore, and non-release notice. Local runs: each plugin pyproject green; planted sase>=99 red with DEPENDENCY_UNPUBLISHED sase>=99: newest published is 0.18.0. sase tool run check passed in sase, sase-github, sase-telegram, and sase-research-artifacts. epic-symbols: none.

## Dependencies

- **Blocks:** [sase-1my.5](sase-1my.5.md) ◐ · ⧖ 2026-10-19
- **Blocks:** [sase-1my.6](sase-1my.6.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1my.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1my.3/README.md) | [sase-1my.3](sase-1my.3.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2d7c282`](https://github.com/sase-org/sase/commit/2d7c282b24e7f8cafe413f283980a9bd074851b6) | feat(release): add shared plugin release-dependency-floor check | [sase-1my.3](sase-1my.3.md) | 2026-10-19 11:53:40 EDT |
| sase-github | [`sase-github@e4f8bf4`](https://github.com/sase-org/sase-github/commit/e4f8bf47c8b0e89b3b46b35369e3574fcf97d0ed) | ci: call the shared release-dependency-floor check | [sase-1my.3](sase-1my.3.md) | 2026-10-19 11:58:13 EDT |
| sase-research-artifacts | [`sase-research-artifacts@0189278`](https://github.com/sase-org/sase-research-artifacts/commit/01892780223a935cde39e31223535d3197a19b11) | ci: call the shared release-dependency-floor check | [sase-1my.3](sase-1my.3.md) | 2026-10-19 12:01:36 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1my.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1my.3/README.md

<!-- sase:referenced-by:end -->

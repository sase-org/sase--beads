# Bead: sase-1nn.1 — Repair sase-core's release-plz merge filter

[Bead Pages](../README.md) / [sase-1nn](README.md) / sase-1nn.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.137](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.137.md) · **Assignee:** `sase-1nn.1` · **Size:** small
**Created:** 2026-10-23 11:30:05 EDT · **Closed:** 2026-10-23 11:54:42 EDT
**Plan:** [202610/v0\_18\_1\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release.md)

## Description

core-merge: fix the invalid jq escape in sase-core's release_plz_merge.py PR filter and pin it with a jq-backed regression test.

## Notes

[2026-10-23T15:54:42Z · sase-1nn.1] Fixed the release-plz PR filter to use jq-safe [.] character classes; added real-jq regression coverage for a valid PR, malformed version separator, wrong head ref, missing marker, and empty list; updated the cadence guard for the new regex. Verified ./scripts/check.sh script-test (107 passed), targeted release filter tests (7 passed), git diff --check, and sase tool run check (ToolRun f14db9d1b93453e58cccfc3b819f6aba succeeded).

## Dependencies

- **Blocks:** [sase-1nn.2](sase-1nn.2.md) ◐ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.1/README.md) | [sase-1nn.1](sase-1nn.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@db2ce63`](https://github.com/sase-org/sase-core/commit/db2ce6375a7bb92c7218d6190f2a6346952e6ad5) | fix(release): make release-plz PR filter jq-safe | [sase-1nn.1](sase-1nn.1.md) | 2026-10-23 11:55:15 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nn.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.1/README.md

<!-- sase:referenced-by:end -->

# Bead: sase-1mk.1 — Make the core non-UTF-8 snapshot fixture filesystem-independent

[Bead Pages](../README.md) / [sase-1mk](README.md) / sase-1mk.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11b.md) · **Assignee:** `sase-1mk.1` · **Size:** small
**Created:** 2026-10-18 09:58:29 EDT · **Closed:** 2026-10-18 10:16:09 EDT
**Plan:** [202610/ship\_v0\_18\_0\_owned\_blockers.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_owned_blockers.md)

## Description

core-fixture: build the non-UTF-8 path into the Git index without writing it to disk, so sase-core's macOS CI and the 0.42.0 cut go green.

## Notes

[2026-10-18T14:16:02Z · sase-1mk.1] Rewrote the non-UTF-8 snapshot test to stage src/\xff.rs only in the Git index (hash-object -w + update-index --cacheinfo, helper stage_blob_at_raw_path in project_stats/test_support.rs); odd name.rs stays on disk, both assertions kept. Audited core tests: no other on-disk filenames macOS/Windows reject (other non-UTF-8 uses are in-memory bytes). Verified: project_stats tests 121 passed, sase tool run check green in core. mac host not tried; core macOS CI is the proof. Noted sase-1m3.7.1.

[2026-10-18T14:16:09Z · sase-1mk.1] Non-UTF-8 fixture now staged via git hash-object/update-index only; project_stats tests (121) and core sase tool run check pass; epic-symbols empty.

## Dependencies

- **Blocks:** [sase-1mk.8](sase-1mk.8.md) ✓ · ⧖ 2026-10-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.1/README.md) | [sase-1mk.1](sase-1mk.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@80dc704`](https://github.com/sase-org/sase-core/commit/80dc704a4f2e1f640f7caa9e578957669c31367d) | test(project-stats): stage non-UTF-8 snapshot fixture path in the Git index only | [sase-1mk.1](sase-1mk.1.md) | 2026-10-18 10:16:36 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1mk.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.1/README.md

<!-- sase:referenced-by:end -->

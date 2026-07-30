# Bead: sase-bd.5 — Projection drift detection and repair

[Bead Pages](../README.md) / [sase-bd](README.md) / sase-bd.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bd.5` · **Size:** medium
**Created:** 2026-07-30 17:44:53 UTC · **Closed:** 2026-07-30 18:48:56 UTC
**Plan:** [202607/bead\_close\_integrity.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_close_integrity.md)

## Description

doctor-projection: teach doctor to compare `issues.jsonl` against the reduction of the canonical streams, census redundant close events with a recent-window rate, and add a guarded `--fix-projection` repair that refuses any diff outside the expected shape.

## Notes

[2026-07-30T18:48:56Z · sase-bd.5] Verified cargo test --workspace in sase-core, focused doctor/open CLI coverage, and full just check (including the 24k+ pytest suite); projection repair is idempotent and refuses row-set, status, unexpected-field, and later-closed_at drift.

## Dependencies

- **Depends on:** [sase-bd.1](sase-bd.1.md) ✓
- **Blocks:** [sase-bd.7](sase-bd.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bd.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bd.5/README.md) | [sase-bd.5](sase-bd.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@6468cb9`](https://github.com/sase-org/sase-core/commit/6468cb90b97394159b03ad2465f3f7b1d2b49770) | feat(beads): report projection drift diagnostics | [sase-bd.5](sase-bd.5.md) | 2026-07-30 18:50:04 |
| sase | [`9fdae1e`](https://github.com/sase-org/sase/commit/9fdae1e1e1349d255f0800d3a4cc481d48159c00) | feat(beads): repair stale event projections | [sase-bd.5](sase-bd.5.md) | 2026-07-30 18:59:54 |

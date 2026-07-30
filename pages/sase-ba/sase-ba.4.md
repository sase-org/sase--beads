# Bead: sase-ba.4 — Retroactive version-control reclaim of the pooled bytes

[Bead Pages](../README.md) / [sase-ba](README.md) / sase-ba.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ba.4` · **Size:** medium
**Created:** 2026-07-30 14:40:49 UTC · **Closed:** 2026-07-30 17:43:41 UTC
**Plan:** [202607/artifact\_store\_lifecycle.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_store_lifecycle.md)

## Description

py-reclaim: add `sase artifact reclaim`, which converts stored automatic rows whose exact content is reproducible from a durable ref into byte-free VCS-backed rows and trashes the redundant copies, reusing the capture policy's git probe and verifying by digest first.

## Notes

[2026-07-30T17:43:41Z · sase-ba.4] Implemented dry-run-first artifact reclaim with durable-ref history discovery, batched digest verification, protected/explicit exclusion, sidecar mapping, VCS replacement-before-trash execution, old/new id reporting, and fail-safe unresolved reasons. Verified 25 focused tests pass; full suite reached 24,390 passed with two unrelated load-sensitive ACE tests that both passed on isolated rerun. Final just check passed formatting, Ruff, mypy, Symvision, size, and other lint stages, stopping only because the concurrent docs phase left five external provider skill copies out of sync; no unrelated skill files were changed. Real-store dry run verified 4,048 reclaimable rows totaling 638,475,351 bytes, with zero unavailable protection sources; no apply was run.

[2026-07-30T17:45:23Z · sase-ba.4] Finalizer reverified: 25 focused tests passed; full suite recorded 24,390 passes with two unrelated load-sensitive ACE cases passing in isolation; real-store dry run found 4,048 rows / 638,475,351 bytes with zero unavailable protection sources and performed no apply.

## Dependencies

- **Depends on:** [sase-ba.3](sase-ba.3.md) ✓
- **Blocks:** [sase-ba.6](sase-ba.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ba.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ba.4/README.md) | [sase-ba.4](sase-ba.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`ac2d5b2`](https://github.com/sase-org/sase/commit/ac2d5b22cf2d4cc0c0c25f5accb039d9118cee79) | feat(artifact): reclaim stored bytes from durable VCS | [sase-ba.4](sase-ba.4.md) | 2026-07-30 17:46:01 |

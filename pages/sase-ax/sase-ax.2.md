# Bead: sase-ax.2 — Three record fields, tolerant reader, preserving writer, backfill library

[Bead Pages](../README.md) / [sase-ax](README.md) / sase-ax.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ax.2` · **Size:** medium
**Created:** 2026-07-29 21:06:38 UTC · **Closed:** 2026-07-29 21:34:25 UTC
**Plan:** [202607/artifact\_read\_cli.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_read_cli.md)

## Description

record-enrichment: add optional sha256, size_bytes, and mime_type to the Python ArtifactFile record, populate them at store time by reusing the already-computed digest, make the index reader range-tolerant and the writer preserve unknown-version rows, and build the inspect/backfill/verify library with tests.

## Notes

[2026-07-29T21:34:25Z · sase-ax.2] Implemented optional sha256/size_bytes/mime_type round-tripping and store-time population, schema v1-v2 tolerant reads, verbatim unsupported-row preservation, and inspect/backfill/verify library coverage. Verified 19 focused tests pass twice; Ruff, mypy, Symvision, git diff check, and committed-plan validation pass. Full suite: 23,849 passed, 7 skipped, with one reproducible unrelated task-list baseline failure. just check is additionally blocked by pre-existing artifact_refs.py 1,115-line toobig violation; sase validate reports existing reciprocal prompt-link errors in artifact_read_cli and preview_panel_reader plans.

[2026-07-29T21:35:13Z · sase-ax.2] Verified 19 focused tests pass twice; Ruff, mypy, Symvision, committed-plan validation, and diff checks pass. Full suite reached 23,849 passes and 7 skips with one reproducible unrelated task-list baseline failure; repository-wide check also encounters pre-existing file-size and plan-link validation blockers.

## Dependencies

- **Blocks:** [sase-ax.3](sase-ax.3.md) ✓

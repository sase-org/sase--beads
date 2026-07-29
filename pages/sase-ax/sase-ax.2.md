# Bead: sase-ax.2 — Three record fields, tolerant reader, preserving writer, backfill library

[Bead Pages](../README.md) / [sase-ax](README.md) / sase-ax.2

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ax.2` · **Size:** medium
**Created:** 2026-07-29 21:06:38 UTC
**Plan:** [202607/artifact\_read\_cli.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_read_cli.md)

## Description

record-enrichment: add optional sha256, size_bytes, and mime_type to the Python ArtifactFile record, populate them at store time by reusing the already-computed digest, make the index reader range-tolerant and the writer preserve unknown-version rows, and build the inspect/backfill/verify library with tests.

## Dependencies

- **Blocks:** [sase-ax.3](sase-ax.3.md) ◐

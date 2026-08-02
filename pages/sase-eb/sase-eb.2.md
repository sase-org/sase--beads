# Bead: sase-eb.2 — Definition resolution, provenance, and the JSON record

[Bead Pages](../README.md) / [sase-eb](README.md) / sase-eb.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.s3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.s3/README.md) · **Assignee:** `sase-eb.2` · **Size:** medium
**Created:** 2026-08-02 15:49:59 UTC · **Closed:** 2026-08-02 16:52:28 UTC
**Plan:** [202608/xprompt\_show.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_show.md)

## Description

resolve: add name normalization and lookup with suggestions, source classification and provenance (path, line, hosted URL, editability), byte-faithful raw-definition extraction for every source bucket, the reference scan, and the versioned show record with its JSON projection.

## Notes

[2026-08-02T16:52:28Z · sase-eb.2] Implemented name normalization/lookup, source provenance and hosted-link best effort, byte-faithful raw extraction, reference scanning, shared workflow step typing, and schema-v1 JSON records. Verified focused resolver/source/config/list suites (62 passed), catalog regression coverage (27 passed), the load-sensitive contention regression independently (1 passed), a real built-in #t resolver smoke, git diff --check, and the final full just check including visual tests.

[2026-08-02T16:53:28Z · sase-eb.2] Implemented definition resolution and schema-v1 show records with byte-faithful raw extraction, shared workflow step typing, and public source/config helpers; verified targeted suites, a real-catalog #t smoke test, and final just check including 25k+ tests and visual snapshots.

## Dependencies

- **Blocks:** [sase-eb.3](sase-eb.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-eb.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-eb.2/README.md) | [sase-eb.2](sase-eb.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`98f2af2`](https://github.com/sase-org/sase/commit/98f2af2fd7a012ca2a8f7093bb6ea3e8d31360d3) | feat(xprompt): add show definition resolver | [sase-eb.2](sase-eb.2.md) | 2026-08-02 16:55:19 |

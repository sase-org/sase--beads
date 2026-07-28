# Bead: sase-ag.5 — Tree-wide refresh and parent-property migration

[Bead Pages](../README.md) / [sase-ag](README.md) / sase-ag.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ag.5` · **Size:** medium
**Created:** 2026-07-28 13:49:33 UTC · **Closed:** 2026-07-28 16:24:34 UTC
**Plan:** [202607/plan\_header\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202607/plan_header_provenance.md)

## Description

reconcile: add sase plan links refresh for bulk, idempotent header reconciliation, migrate existing parent frontmatter into PARENT bullets, and deprecate the frontmatter property in the plan schema.

## Notes

[2026-07-28T16:24:25Z · sase-ag.5] Implemented tree-wide plan provenance refresh and parent-property migration. Added 'sase plan links refresh' with dry-run default, --write, --plan, --path, and JSON reporting; one-pass association indexing; PARENT/AGENTS/COMMITS reconciliation; legacy parent deprecation/validation; and batched formatting/commit behavior. Updated Rust core artifact-link and validation contracts plus Python callers/tests. Migrated the live plans sidecar: 3,240 plans scanned, 1,290 changed, no warnings/errors, committed and pushed as 2cafce89; a second full dry-run reported zero changes. Verification: just rust-check passed (fmt, clippy -D warnings, all workspace tests); targeted Python tests passed; just check passed all non-test gates and completed 23,066 tests successfully with only the concurrency-sensitive suite-gate integration test failing in the aggregate run, then passing independently with the same -n 28 worker configuration. git diff --check passed in both repositories.

## Dependencies

- **Depends on:** [sase-ag.4](sase-ag.4.md) ✓
- **Blocks:** [sase-ag.6](sase-ag.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ag.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ag.5/README.md) | [sase-ag.5](sase-ag.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`ca29de3`](https://github.com/sase-org/sase/commit/ca29de3befeea34321826e749ffc1e689a8a8b5e) | feat(plan): add bulk provenance link refresh (sase-ag.5) | [sase-ag.5](sase-ag.5.md) | 2026-07-28 16:26:46 |

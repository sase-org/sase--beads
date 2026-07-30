# Bead: sase-bb.3 — Python bead refs, show, and doctor

[Bead Pages](../README.md) / [sase-bb](README.md) / sase-bb.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bb.3` · **Size:** medium
**Created:** 2026-07-30 14:53:50 UTC · **Closed:** 2026-07-30 16:37:03 UTC
**Plan:** [202607/spec\_artifact\_references.md](https://github.com/sase-org/sase--plans/blob/main/202607/spec_artifact_references.md)

## Description

beads: raise the core floor, add the Python reference-list facade, mirror the new bead field across the model, codecs, and JSON wire, render a resolved REFS section in `sase bead show`, and thread the reference context into `sase bead doctor`.

## Notes

[2026-07-30T16:37:03Z · sase-bb.3] Implemented Python bead artifact references end-to-end: create/ref add/list/rm, persisted refs across model/SQLite/JSONL/Rust wire, resolved REFS display and search, and reference-aware doctor diagnostics; raised the core floor to 0.14. Verified 129 focused tests, the final query-facade file (8 passed), a full suite with 24,335 other tests passed and 7 skipped, Rust fmt/clippy/workspace tests, git diff checks, and all just-check quality stages. The remaining SASE validation failures are pre-existing external provider skill drift and unrelated July plan backlinks.

## Dependencies

- **Depends on:** [sase-bb.2](sase-bb.2.md) ✓
- **Blocks:** [sase-bb.4](sase-bb.4.md) ◐
- **Blocks:** [sase-bb.5](sase-bb.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bb.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bb.3/README.md) | [sase-bb.3](sase-bb.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@d9e4fca`](https://github.com/sase-org/sase-core/commit/d9e4fca4adfe3edaa6ec16c9e171d98ae743906d) | fix(bead): preserve refs and expose doctor context | [sase-bb.3](sase-bb.3.md) | 2026-07-30 16:38:20 |

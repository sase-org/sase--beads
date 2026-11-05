# Bead: sase-1rd.3 — Hourly preview emits an actionable, beautiful notification

[Bead Pages](../README.md) / [sase-1rd](README.md) / sase-1rd.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.18e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.18e.md) · **Assignee:** `sase-1rd.3` · **Size:** small
**Created:** 2026-11-05 06:20:14 EST
**Plan:** [202611/actionable\_run\_prune\_notifications.md](https://github.com/sase-org/sase--plans/blob/main/202611/actionable_run_prune_notifications.md)

## Description

preview_notification: the chop purges expired batches, writes a review snapshot, and attaches the review payload. It redesigns the report with project display names and per-project rows, supersedes stale previews, and drops the "preview-only" copy.

## Notes

[2026-11-05T16:17:25Z · sase-1rd.3] PROPOSED FOLLOW-UP: After the local Justfile removal/re-key lands on the default branch, rerun `sase bead epic-symbols sase-1rd.3` and close this phase. The close guard still sees the three old `origin/master` entries for write_snapshot, encode_run_prune_review, and snapshot_dir, even though the local Justfile no longer keys them to this phase.

## Dependencies

- **Depends on:** [sase-1rd.2](sase-1rd.2.md) ✓ · ⧖ 2026-11-05
- **Blocks:** [sase-1rd.4](sase-1rd.4.md) ◐ · ⧖ 2026-11-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rd.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rd.3/README.md) | [sase-1rd.3](sase-1rd.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`950c8ae`](https://github.com/sase-org/sase/commit/950c8aec15f1e20c93b4a67d7564d09f47d8c137) | feat(artifact-retention): make run prune previews actionable | [sase-1rd.3](sase-1rd.3.md) | 2026-11-05 11:18:57 EST |

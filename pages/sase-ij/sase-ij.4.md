# Bead: sase-ij.4 — Ratchet the window on the pending release branch in report-only mode

[Bead Pages](../README.md) / [sase-ij](README.md) / sase-ij.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.4` · **Size:** medium
**Created:** 2026-08-09 15:19:11 EDT · **Closed:** 2026-08-09 16:28:05 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

release-ratchet: extend publish.yml's sync-lockfile job into a sync-release-metadata reconciler that runs the ratchet tool ahead of the lock refresh, landing it in report-only mode so a real release can be observed before it writes anything.

## Notes

[2026-08-09T20:28:05Z · sase-ij.4] Implemented sync-release-metadata with report-only ratchet before uv lock; verified focused workflow pytest, scratch reconciler dry run no-op at sase-core-rs 0.21.3, and just check.

[2026-08-09T20:29:22Z · sase-ij.4] Verified focused publish workflow test, scratch release-metadata reconciler dry run, and full just check.

## Dependencies

- **Depends on:** [sase-ij.2](sase-ij.2.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ij.5](sase-ij.5.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.4/README.md) | [sase-ij.4](sase-ij.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dfa07fb`](https://github.com/sase-org/sase/commit/dfa07fb48e7c215c6470ea9364b9f118a62bd50e) | ci: reconcile release metadata on pending branch | [sase-ij.4](sase-ij.4.md) | 2026-08-09 16:30:31 EDT |

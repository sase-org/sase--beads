# Bead: sase-k2.5 — Adopted external Patches track their pull request

[Bead Pages](../README.md) / [sase-k2](README.md) / sase-k2.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yn/README.md) · **Assignee:** `sase-k2.5` · **Size:** large
**Created:** 2026-08-12 11:30:39 EDT · **Closed:** 2026-08-12 13:28:06 EDT
**Plan:** [202608/external\_mirror\_refinement.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_mirror_refinement.md)

## Description

patch_status: add the refresh action the external PR classifier is missing so an already-adopted Patch follows its PR from open to merged or closed and moves from the active ProjectSpec into the archive, across the sase-core wire and the Python importer.

## Notes

[2026-08-12T17:28:06Z · sase-k2.5] Implemented refresh action end-to-end: sase-core classifier/wire (schema v2, refresh vs skip for owned external Patches, 6 new Rust unit tests) plus Python wire/classifier parity, importer._refresh_existing_patch with re-ownership guard and active->archive move, MirrorReport.refreshed threaded through pr_sync budget/dry-run accounting and the sync-external CLI table, and 12 new focused importer/sync/parity tests. Verified: sase-core 'just check' green; SASE workspace 'just install' + 29 focused external-PR tests + whole-repo 'just check' (fmt/lint/mypy/symvision/toobig/SASE validation/scoped tests) all green.

## Dependencies

- **Depends on:** [sase-k2.1](sase-k2.1.md) ✓ · ⧖ 2026-08-12
- **Depends on:** [sase-k2.2](sase-k2.2.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-k2.6](sase-k2.6.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k2.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-k2.5.md) | [sase-k2.5](sase-k2.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0567ce0`](https://github.com/sase-org/sase/commit/0567ce03be8450a991ec296494dbb8d185804d96) | feat(external-mirror): refresh adopted external Patches from PR state | [sase-k2.5](sase-k2.5.md) | 2026-08-12 13:29:25 EDT |
| sase-core | [`sase-core@fb3c869`](https://github.com/sase-org/sase-core/commit/fb3c869810eb632415d170d126d866820957a4d5) | feat(external-pr): classify refresh actions for adopted external Patches | [sase-k2.5](sase-k2.5.md) | 2026-08-12 13:31:02 EDT |

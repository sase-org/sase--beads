# Bead: sase-1m3.7.1.2 — Committed-tree snapshots and incremental blob cache

[Bead Pages](../README.md) / [sase-1m3.7.1](sase-1m3.7.1.md) / sase-1m3.7.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1m3.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.md) · **Assignee:** `sase-1m3.7.1.2` · **Size:** medium
**Created:** 2026-10-17 02:56:51 EDT · **Closed:** 2026-10-17 09:20:59 EDT
**Plan:** [202610/project\_stats\_code\_records.md](https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_code_records.md)

## Description

code-snapshot: enumerate committed trees, resolve committed attributes, measure bounded blob batches, and cache per-path results with correct attribute and classifier invalidation.

## Notes

[2026-10-17T12:48:04Z · sase-1m3.7.1.2] Implemented committed-tree code snapshots in sase-core: NUL-safe ls-tree, isolated check-attr --source, bounded cat-file batches, and a kind-namespaced incremental cache. Targeted just test -p sase_core snapshot::tests passed (empty/zero-code repos, roles, gitlink/symlink, dirty vs committed attrs, info/user attribute isolation, explicit false overrides, binary/LFS/oversize, cache reuse after edit/rename/delete/attribute-only commits, blob-OID request seam, corrupt/version rebuild). epic-symbols has no leftovers. Full sase-core just check follows via prepared monitor.

[2026-10-17T13:03:28Z · sase-1m3.7.1.2--1] just check failed on clippy::manual_repeat_n in snapshot/blobs.rs test helper; replaced repeat().take(40) with repeat_n. just clippy now passes. Re-running full sase-core just check via prepared monitor.

[2026-10-17T13:20:59Z · sase-1m3.7.1.2--2] Verified committed-tree code snapshots in sase-core: NUL-safe ls-tree, isolated check-attr --source, bounded cat-file batches, and a kind-namespaced incremental cache. Tests cover empty/zero-code repos, roles, gitlink/symlink, dirty vs committed attrs, info/user isolation, explicit false overrides, binary/LFS/oversize, cache reuse after edit/rename/delete/attribute-only commits, blob-OID request seam, and corrupt/version rebuild. epic-symbols has no leftovers. sase-core just check passed (monitor 3jtfzjm4zwmc, exit 0) after clippy::manual_repeat_n repair in snapshot/blobs.rs.

## Dependencies

- **Depends on:** [sase-1m3.7.1.1](sase-1m3.7.1.1.md) ✓ · ⧖ 2026-10-17
- **Blocks:** [sase-1m3.7.1.4](sase-1m3.7.1.4.md) ◐ · ⧖ 2026-10-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.7.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.1.2.md) | [sase-1m3.7.1.2](sase-1m3.7.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@733256e`](https://github.com/sase-org/sase-core/commit/733256ede964bc99e46f8ce7faffb690df0c6a49) | feat(project-stats): add committed-tree code snapshots and incremental blob cache | [sase-1m3.7.1.2](sase-1m3.7.1.2.md) | 2026-10-17 09:44:30 EDT |

# Bead: sase-1lh.7.5.4.3.3.4.4.1 — Promote variadic openat modes without changing permissions

[Bead Pages](../README.md) / [sase-1lh.7.5.4.3.3.4.4](sase-1lh.7.5.4.3.3.4.4.md) / sase-1lh.7.5.4.3.3.4.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.7.5.4.3.3.4.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.5.4.3.3.4.land.md) · **Assignee:** `sase-1lh.7.5.4.3.3.4.4.1` · **Size:** small
**Created:** 2026-10-17 21:56:53 EDT · **Closed:** 2026-10-17 22:16:45 EDT
**Plan:** [202610/finish\_portable\_core\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_portable_core_release.md)

## Description

core: repair the macOS E0617 regression in mobile pairing and verify the core.

## Notes

[2026-10-18T02:16:32Z · sase-1lh.7.5.4.3.3.4.4.1] core repair complete on linked sase-core master dd56b94a (PR #331 still only the 0.42.0 release chore 0b23a739; no concurrent openat fix). Both O_CREAT openat calls now pass openat_creat_mode(PROTECTED_FILE_MODE) -> libc::c_uint (lossless From; targeted clippy::useless_conversion for Linux identity). mkdirat/fchmod keep native mode_t. Comment no longer claims native mode_t is valid for every syscall. Module audit: only those two openat calls take a mode (open/openat without O_CREAT have no mode operand). just fmt; just test -p sase_core mobile_pairing: 28 passed including issue_under_permissive_umask_creates_restrictive_modes (0700/0600/0600), pairing_dir_symlink_is_rejected, store_file_symlink_is_rejected, insecure lock/store, world-writable containing dir. just fast -p sase_core --target aarch64-apple-darwin blocked at libsqlite3-sys cc -arch (not macOS proof). sase tool run check aa65464aec20930adefb4ab99a8926a6 succeeded/exit 0 (8m52s) from the linked checkout. Linux pass is not macOS CI; watch phase must confirm job 117510033363-class macOS compile. Did not pin sase, wait on this commit, or edit release metadata.

[2026-10-18T02:16:45Z · sase-1lh.7.5.4.3.3.4.4.1] Promoted both O_CREAT openat modes to c_uint via lossless From; mkdirat/fchmod stay mode_t. mobile_pairing tests (umask 0700/0600, symlink, permissions) passed; sase tool run check aa65464aec20930adefb4ab99a8926a6 exit 0. macOS cross-check blocked at SQLite; real macOS CI remains the watch phase.

## Dependencies

- **Blocks:** [sase-1lh.7.5.4.3.3.4.4.2](sase-1lh.7.5.4.3.3.4.4.2.md) ✓ · ⧖ 2026-10-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.5.4.3.3.4.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.5.4.3.3.4.4.1/README.md) | [sase-1lh.7.5.4.3.3.4.4.1](sase-1lh.7.5.4.3.3.4.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@72bf920`](https://github.com/sase-org/sase-core/commit/72bf9203758d7986da1cb6d14b5d13f00327de08) | fix(mobile-pairing): promote variadic openat modes to c\_uint | [sase-1lh.7.5.4.3.3.4.4.1](sase-1lh.7.5.4.3.3.4.4.1.md) | 2026-10-17 22:17:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lh.7.5.4.3.3.4.4.1][1] | Need remaining bead notes, DECISIONS, and design details | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.5.4.3.3.4.4.1/README.md

<!-- sase:referenced-by:end -->

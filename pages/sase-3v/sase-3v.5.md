# Bead: sase-3v.5 — Phase 5: Remove Hook Configuration and Compatibility Dependence

[Bead Pages](../README.md) / [sase-3v](README.md) / sase-3v.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-3v.5`
**Created:** 2026-05-21 23:13:26 UTC · **Closed:** 2026-05-22 00:46:16 UTC
**Plan:** [202605/commit\_finalizer\_no\_stop\_hooks.md](https://github.com/sase-org/sase--plans/blob/main/202605/commit_finalizer_no_stop_hooks.md)

## Notes

COMMIT: 16de3ab08

[2026-07-27T19:01:12Z · sase-a1.6] [2026-05-22T00:44:11Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Removed SASE provider-native stop-hook references from repo-local and chezmoi-managed agent configs, applied chezmoi changes, scoped retained hook scripts as compatibility-only, removed the Codex configured sibling-hook fallback test path, and added static repo-local hook config coverage. Verification: focused pytest passed; applied configs contain no SASE stop-hook references; SASE just check passed; chezmoi just check passed with isolated XDG_DATA_HOME to avoid live Neovim smart-open sqlite lock.

## Dependencies

- **Depends on:** [sase-3v.4](sase-3v.4.md) ✓
- **Blocks:** [sase-3v.6](sase-3v.6.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`479549a`](https://github.com/sase-org/sase/commit/479549a0c60df14388a2e63f4c29fb7a21eae7c8) | feat: remove SASE stop hook configuration (sase-3v.5) | [sase-3v.5](sase-3v.5.md) | 2026-05-22 00:46:41 |

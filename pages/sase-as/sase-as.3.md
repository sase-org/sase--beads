# Bead: sase-as.3 — Anchored artifact-file path copy

[Bead Pages](../README.md) / [sase-as](README.md) / sase-as.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-as.3` · **Size:** small
**Created:** 2026-07-29 14:31:07 UTC · **Closed:** 2026-07-29 14:57:34 UTC
**Plan:** [202607/artifact\_tranche\_zero\_and\_generic\_sidecar\_roles.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_tranche_zero_and_generic_sidecar_roles.md)

## Description

path-copy: stop emitting bare workspace-relative paths from the artifact-file modal's path copy, prefer the always-present stored path, anchor any source-path answer, and say in the toast which of the two was copied.

## Notes

[2026-07-29T14:57:34Z · sase-as.3] Rewrote _artifact_file_clipboard_path in src/sase/ace/tui/modals/artifact_files_modal.py: Y now prefers the always-present stored path, keeps the PDF source-path special case, always emits an anchored (home-relative/absolute) path, and deletes _workspace_relative_path so no bare workspace-relative path can be copied. The toast names which path was copied (stored vs source) and warns when a chosen source path no longer exists. Rewrote the 4 tests asserting the old contract with names stating the new one, and added regressions for a recycled-workspace source_path and a missing source path (10 passed). just check is green through fmt/lint/mypy/symvision/toobig; the SASE-validation step and the 5 axe PNG snapshot failures are pre-existing on a clean tree (verified via git stash) and unrelated to this phase.

# Bead: sase-ay.5 — Warm local path inventory for the prompt

[Bead Pages](../README.md) / [sase-ay](README.md) / sase-ay.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ay.5` · **Size:** medium
**Created:** 2026-07-29 22:24:56 UTC · **Closed:** 2026-07-29 22:54:11 UTC
**Plan:** [202607/at\_reference\_completion\_menu.md](https://github.com/sase-org/sase--plans/blob/main/202607/at_reference_completion_menu.md)

## Description

tui_paths: add a mtime-validated directory-listing snapshot cache with a background loader, a loading row, and warm-on-focus, so prompt path rows never touch disk from a keystroke.

## Notes

[2026-07-29T22:54:11Z · sase-ay.5] Implemented bounded mtime/inode-validated prompt path snapshots, coalesced threaded loading/revalidation, matching-menu refresh, and warm-on-focus hooks. Verified just lint and formatting/diff checks; 50 targeted prompt inventory/file/artifact tests passed. Full just test reached 23,881 passed and 7 skipped with one unrelated input-collection timing failure that passed in isolation. Full just check cleared all lint stages but SASE validation is externally blocked by missing reciprocal prompt links in the clean plans sidecar.

## Dependencies

- **Blocks:** [sase-ay.6](sase-ay.6.md) ◐

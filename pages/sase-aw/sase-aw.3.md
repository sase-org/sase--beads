# Bead: sase-aw.3 — In-document search with slash, n, N

[Bead Pages](../README.md) / [sase-aw](README.md) / sase-aw.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-aw.3` · **Size:** medium
**Created:** 2026-07-29 20:59:09 UTC · **Closed:** 2026-07-29 23:08:23 UTC
**Plan:** [202607/preview\_panel\_reader.md](https://github.com/sase-org/sase--plans/blob/main/202607/preview_panel_reader.md)

## Description

reader-search: add a hidden commit-on-enter search input with smartcase substring matching over the source view, worker-computed match lines and wrapped-row offset maps, all-match highlighting through a lazy_renderable highlight_lines extension, centered n/N jumps with wraparound, an escape ladder, rendered-to-source auto-switch, perf guards, and unit/pilot/PNG tests plus docs.

## Notes

[2026-07-29T23:08:23Z · sase-aw.3] Implemented commit-on-enter smartcase preview search with off-thread match/wrap computation, source highlighting, centered n/N wraparound navigation, escape ladder, rendered-to-source switching, capped-output warnings, docs/help, and PNG coverage. Verified just lint; committed-plan validation; 53 focused unit/pilot tests; 6 preview/help visual tests; and a full run with 23,891 passed / 7 skipped whose sole failure was the intentional help golden drift, then updated and reverified. just check's remaining SASE validation failure is unrelated: missing prompt backlinks in at_reference_completion_menu.md.

[2026-07-29T23:09:42Z · sase-aw.3] Verified smartcase source search, off-thread wrapping and match calculation, highlighting and navigation, escape/copy-mode behavior, capped-output warnings, docs/help, and PNG snapshots; just lint passed, 53 focused tests passed, 6 relevant visual tests passed, and the full suite reached 23,891 passed with 7 skipped apart from the accepted intentional help snapshot drift.

## Dependencies

- **Depends on:** [sase-aw.1](sase-aw.1.md) ✓
- **Depends on:** [sase-aw.2](sase-aw.2.md) ✓

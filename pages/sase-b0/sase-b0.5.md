# Bead: sase-b0.5 — Smart open, viewer hand-off, external open, and agent jump

[Bead Pages](../README.md) / [sase-b0](README.md) / sase-b0.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b0.5` · **Size:** medium
**Created:** 2026-07-29 23:14:06 UTC · **Closed:** 2026-07-30 01:03:41 UTC
**Plan:** [202607/artifacts\_files\_subtab.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifacts_files_subtab.md)

## Description

open-actions: implement smart enter dispatch — preview reader for text-like files, rich terminal viewer for media — plus Z viewer hand-off for one row or the marked set, o open-external, and a jump-to-producing-agent with revival.

## Notes

[2026-07-30T01:03:41Z · sase-b0.5] Implemented smart enter preview/media dispatch, visible-marked Z viewer hand-off, editor/xdg-open external opening, and live/dismissed producing-agent jump. Verified 46 focused/related tests; full just test passed 24,021 tests with 7 skipped; formatting, Ruff, mypy, Symvision, and size gates pass. just check reaches SASE validation and is blocked only by six unchanged plans-sidecar prompt-link errors.

## Dependencies

- **Depends on:** [sase-b0.2](sase-b0.2.md) ✓
- **Blocks:** [sase-b0.6](sase-b0.6.md) ✓

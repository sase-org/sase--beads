# Bead: sase-ar.4 — PNG snapshot coverage for chop reports

[Bead Pages](../README.md) / [sase-ar](README.md) / sase-ar.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ar.4` · **Size:** small
**Created:** 2026-07-29 13:50:06 UTC · **Closed:** 2026-07-29 14:57:43 UTC
**Plan:** [202607/axe\_chop\_reports.md](https://github.com/sase-org/sase--plans/blob/main/202607/axe_chop_reports.md)

## Description

visual: add AXE-tab PNG snapshot fixtures and goldens covering a report-rich run, a report-less run, a failing run, and a narrow terminal.

## Notes

[2026-07-29T14:57:43Z · sase-ar.4] Implemented AXE chop report PNG fixtures/goldens; verified with just install, just fmt-py, and just test-visual -- tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py (7 passed), and inspected rich/absent/error/narrow PNGs. just check reached validation and failed on pre-existing external/generated validation issues: init skills provider files out of date and axe_chop_reports plan/prompt links missing.

## Dependencies

- **Depends on:** [sase-ar.3](sase-ar.3.md) ✓
- **Blocks:** [sase-ar.6](sase-ar.6.md) ✓

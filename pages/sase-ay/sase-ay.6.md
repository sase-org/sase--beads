# Bead: sase-ay.6 — TUI reference menu behavior

[Bead Pages](../README.md) / [sase-ay](README.md) / sase-ay.6

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ay.6` · **Size:** medium
**Created:** 2026-07-29 22:25:09 UTC · **Closed:** 2026-07-29 23:41:36 UTC
**Plan:** [202607/at\_reference\_completion\_menu.md](https://github.com/sase-org/sase--plans/blob/main/202607/at_reference_completion_menu.md)

## Description

tui_menu: rewire the TUI provider onto the shared binding, open on a bare `@`, merge the warm path inventory, and define accept, dismissal, and Enter-ownership rules.

## Notes

[2026-07-29T23:41:36Z · sase-ay.6] Verified 59 focused TUI completion/path tests pass; Ruff, mypy, and Symvision are clean. Full suite reached 23,947 passes; remaining failures were two pre-existing artifact-ref API test mismatches plus one suite-gate timeout. just check reached SASE validation and is blocked only by external generated-skill and SDD plan-link drift.

## Dependencies

- **Depends on:** [sase-ay.2](sase-ay.2.md) ✓
- **Depends on:** [sase-ay.5](sase-ay.5.md) ✓
- **Blocks:** [sase-ay.7](sase-ay.7.md) ✓

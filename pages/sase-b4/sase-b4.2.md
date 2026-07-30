# Bead: sase-b4.2 — ACE prompt gating and the Ctrl+T reveal

[Bead Pages](../README.md) / [sase-b4](README.md) / sase-b4.2

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b4.2` · **Size:** medium
**Created:** 2026-07-30 11:15:08 UTC
**Plan:** [202607/at\_reference\_file\_row\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202607/at_reference_file_row_gate.md)

## Description

tui-gate: thread the new menu option through the Python artifact-ref facade and prompt completion mixins, add a per-menu "files revealed" state that a first `Ctrl+T` press sets instead of force-completing, surface a `[^T] files` panel hint, and refresh the affected tests and docs.

## Dependencies

- **Depends on:** [sase-b4.1](sase-b4.1.md) ✓
- **Blocks:** [sase-b4.3](sase-b4.3.md) ◐

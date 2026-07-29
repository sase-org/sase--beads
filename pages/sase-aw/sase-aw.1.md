# Bead: sase-aw.1 — Reader core — copy, editor, viewer hand-off, reference-aware chrome

[Bead Pages](../README.md) / [sase-aw](README.md) / sase-aw.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-aw.1` · **Size:** medium
**Created:** 2026-07-29 20:59:03 UTC · **Closed:** 2026-07-29 21:22:04 UTC
**Plan:** [202607/preview\_panel\_reader.md](https://github.com/sase-org/sase--plans/blob/main/202607/preview_panel_reader.md)

## Description

reader-core: add a reference field to PreviewPayload (chats/plans callers fill it best-effort), adopt CopyModeForwardingMixin for the % menu, add y/Y copy actions, o open-in-$EDITOR, Z terminal-viewer hand-off via a shared path helper, a reference→path title line, a dynamic footer, docs/help sweeps, and unit/pilot/PNG tests.

## Notes

[2026-07-29T21:22:04Z · sase-aw.1] Implemented the reader core: reference-aware payloads for chats/plans, pump-free y/Y copy, forwarded % copy mode, editor and shared rich-viewer handoffs, dynamic title/footer chrome, docs/help updates, and unit/pilot/PNG coverage. Verified 25 focused tests pass; 4 preview PNG tests pass in non-update mode and goldens were visually inspected; Ruff, mypy, formatting, keep-sorted, script, and changelog checks pass. Full suite reached 23,848 passed/7 skipped with three unrelated failures; both timing failures passed serially, while the remaining task-list test independently reproduces an 80-column Rich label truncation. Full just check is blocked by pre-existing stale sase-av Symvision exemptions after that prerequisite epic was closed.

[2026-07-29T21:22:58Z · sase-aw.1] Verified 25 focused behavior tests and 4 preview PNG tests; Ruff, mypy, formatting, and supporting validations passed. Full suite reached 23,848 passed with three unrelated failures; just check is blocked only by pre-existing stale sase-av Symvision exemptions.

## Dependencies

- **Blocks:** [sase-aw.2](sase-aw.2.md) ✓
- **Blocks:** [sase-aw.3](sase-aw.3.md) ✓

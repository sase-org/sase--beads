# Bead: sase-az.1 — One clipboard delivery seam with OSC 52 and a selectable fallback

[Bead Pages](../README.md) / [sase-az](README.md) / sase-az.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-az.1` · **Size:** medium
**Created:** 2026-07-29 23:12:31 UTC · **Closed:** 2026-07-29 23:49:32 UTC
**Plan:** [202607/copy\_as\_palette.md](https://github.com/sase-org/sase--plans/blob/main/202607/copy_as_palette.md)

## Description

delivery: add a unified copy-delivery module that pairs Textual's OSC 52 write with the verifiable subprocess adapter (plus a tmux load-buffer candidate), reports a typed outcome, standardizes the success/failure toast vocabulary, opens a selectable-text fallback modal when no transport works, and sweeps every TUI copy call site onto the seam and off the message pump.

## Notes

[2026-07-29T23:49:32Z · sase-az.1] Verified tmux-first clipboard candidates, typed verified/osc52_only/failed outcomes, OSC 52 payload guarding, exact selectable fallback recovery, pump-free delivery across ACE copy sites, vim toast fallback, and docs. Scoped clipboard/TUI runs passed (192 tests, plus 38 final seam/file-hint tests). Full suite: 23,954 passed and 7 skipped; its 2 failures are unrelated existing tests for absent artifact_refs._resolve_artifact_ref. just check passes formatting, Ruff, mypy, scripts, changelog, Symvision, and size checks, then stops only on unrelated provider-skill drift and existing SDD plan-link errors.

## Dependencies

- **Blocks:** [sase-az.2](sase-az.2.md) ✓

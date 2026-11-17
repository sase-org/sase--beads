# Bead: sase-1tb.1 — Stop launching mpv in tmux; show a still frame plus metadata

[Bead Pages](../README.md) / [sase-1tb](README.md) / sase-1tb.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1di](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1di.md) · **Assignee:** `sase-1tb.1` · **Size:** medium
**Created:** 2026-11-17 11:16:32 EST
**Plan:** [202611/fast\_video\_artifact\_pane.md](https://github.com/sase-org/sase--plans/blob/main/202611/fast_video_artifact_pane.md)

## Description

tmux-still-hotfix: inside tmux with a kitty VO, render an ffmpeg still plus ffprobe metadata through kitten icat instead of mpv. Make missing tools non-fatal, add ffmpeg/ffprobe doctor rows, fix the Video Preview docs, and ship the pty+tmux regression probe.

## Notes

[2026-11-17T17:11:57Z · sase-1tb.1] tmux-still-hotfix landed: _viewer_video_media.py (guard, ffprobe/ffmpeg builders, metadata parse, still path with non-fatal notices), mpv dispatch unchanged outside tmux / vo!=kitty, doctor ffmpeg+ffprobe rows + mpv reword, Video Preview + ace-behavior docs, 23 unit tests, pty+tmux probe. Measured on athena: header->APC 187ms (SLO 1.0s), spawn->header ~1.1s incl. cold shell+python (viewer-child-startup will trim ~0.55s), client bytes 5640 (<4MB), pane title unchanged, mpv never spawned. Epic-symbol rows added for sase-1tb.4 (VideoMetadata, ffprobe_metadata_command, parse_ffprobe_metadata, probe_video_metadata) and sase-1tb.5 (format_video_metadata_summary); still-extraction trio privatized.

[2026-11-17T17:26:09Z · sase-1tb.1--1] check FAILED on tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget: footprint 11,831,287 vs cap 11,823,363 (+7,924). Base at merge-base is 11,822,908 (455 headroom). tools/tui_import_closure --diff attributes +8,379 to this phase: +7,286 sase.ace.tui.graphics._viewer_video_media (new module pulled in eagerly) + ~1,093 edits across _viewer_render/_viewer_loop_media/_viewer_loop_sequence/_viewer_loop_terminal/_viewer_loop_types. Fix: defer _viewer_video_media (lazy imports in _viewer_loop_media.display_video_artifact and _viewer_loop_sequence, lazy wrapper re-export in _viewer_loop instead of top-level from-import, keep video_vo_uses_kitty_placement out of the heavy module) and shrink the _viewer_render video_config plumbing so edited-module delta fits the 455-byte headroom, then re-run just check.

## Dependencies

- **Blocks:** [sase-1tb.4](sase-1tb.4.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tb.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tb.1.md) | [sase-1tb.1](sase-1tb.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bfa6032`](https://github.com/sase-org/sase/commit/bfa60324a69641e8019e7dd9e60b1f120eed30fc) | feat(viewer): show video still frame with metadata in tmux | [sase-1tb.1](sase-1tb.1.md) | 2026-11-17 12:33:43 EST |

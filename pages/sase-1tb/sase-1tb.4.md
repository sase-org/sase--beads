# Bead: sase-1tb.4 — Persistent frame, scrub-track, and storyboard cache

[Bead Pages](../README.md) / [sase-1tb](README.md) / sase-1tb.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1di](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1di.md) · **Assignee:** `sase-1tb.4` · **Size:** medium
**Created:** 2026-11-17 11:16:33 EST
**Plan:** [202611/fast\_video\_artifact\_pane.md](https://github.com/sase-org/sase--plans/blob/main/202611/fast_video_artifact_pane.md)

## Description

video-frame-cache: add the ffmpeg-backed frame service. It does exact-frame extraction, a low-priority background scrub track, a decile storyboard composed with Pillow, and a content-digest-keyed bounded cache with atomic writes and cancellation.

## Notes

[2026-11-17T19:31:35Z · sase-1tb.4] Implemented _viewer_video_frames.py: extract_frame (input-seek exact frames, PNG, atomic publish), ScrubTrack (single-pass fps=min(2,240/duration) ffmpeg at nice -10/-threads 2, nearest/progress/done/cancel, index-gated cache reuse), build_storyboard (10 deciles, Pillow grid 10x1 or 5x2 with timestamp labels, prefers scrub frames else 4-way concurrent extraction), content-digest-keyed cache (sha256, atomic writes, 256MB LRU eviction), metadata_for_frame_service (payload cache reusing VideoMetadata/ffprobe_metadata_command/parse_ffprobe_metadata/probe_video_metadata). Tests: tests/ace/tui/artifact_file_viewer/test_video_frames.py, 30 fast pass + 1 slow real-ffmpeg test passes. Justfile: dropped 4 sase-1tb.4 epic-symbol rows, added 11 sase-1tb.5 rows. symvision/ruff/mypy clean. just check run 66e2ce4f31477e392cfb2eda0eea104a running; closing after it lands green.

[2026-11-17T19:43:29Z · sase-1tb.4--1] just check green via sase tool run 66e2ce4f31477e392cfb2eda0eea104a (exit 0, all stages pass). Working-tree Justfile has no sase-1tb.4 epic-symbol rows (4 dropped, 12 sase-1tb.5 rows present); sase bead epic-symbols still lists the 4 upstream origin/master rows pending landing, so manual sase bead close refuses until the host lands this tree. Submitting host commit+close.

## Dependencies

- **Depends on:** [sase-1tb.1](sase-1tb.1.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1tb.5](sase-1tb.5.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tb.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tb.4.md) | [sase-1tb.4](sase-1tb.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f2fb7fb`](https://github.com/sase-org/sase/commit/f2fb7fb6b5006fdee544b398fab0f74fecbaa3aa) | feat(viewer): add persistent video frame, scrub-track, and storyboard cache | [sase-1tb.4](sase-1tb.4.md) | 2026-11-17 14:46:04 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tb.1][1] | Check whether the in-progress video-frame-cache phase depends on _viewer_video_media names I plan to move | 1 |
| read-by | [agent:sase-1tb.1--1][1] | conflict repair: verify symvision epic-symbol whitelist bead exists | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tb.1.md

<!-- sase:referenced-by:end -->

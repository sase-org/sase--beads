# Bead: sase-1tb.4 — Persistent frame, scrub-track, and storyboard cache

[Bead Pages](../README.md) / [sase-1tb](README.md) / sase-1tb.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1di](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1di.md) · **Assignee:** `sase-1tb.4` · **Size:** medium
**Created:** 2026-11-17 11:16:33 EST
**Plan:** [202611/fast\_video\_artifact\_pane.md](https://github.com/sase-org/sase--plans/blob/main/202611/fast_video_artifact_pane.md)

## Description

video-frame-cache: add the ffmpeg-backed frame service. It does exact-frame extraction, a low-priority background scrub track, a decile storyboard composed with Pillow, and a content-digest-keyed bounded cache with atomic writes and cancellation.

## Dependencies

- **Depends on:** [sase-1tb.1](sase-1tb.1.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1tb.5](sase-1tb.5.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tb.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tb.4/README.md) | [sase-1tb.4](sase-1tb.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tb.1--1][1] | conflict repair: verify symvision epic-symbol whitelist bead exists | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tb.1.md

<!-- sase:referenced-by:end -->

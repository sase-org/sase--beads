# Bead: sase-1tb.6 — Motion backends, native handoff, and audio semantics

[Bead Pages](../README.md) / [sase-1tb](README.md) / sase-1tb.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1di](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1di.md) · **Assignee:** `sase-1tb.6` · **Size:** medium
**Created:** 2026-11-17 11:16:34 EST · **Closed:** 2026-11-17 18:36:42 EST
**Plan:** [202611/fast\_video\_artifact\_pane.md](https://github.com/sase-org/sase--plans/blob/main/202611/fast_video_artifact_pane.md)

## Description

motion-handoff: add the backend and open_command config keys. mpv runs in-pane only where it can render, with sw-fast, a probed shm flag, and --audio=no. The o key hands off to a native or configured player. Add degraded banners and a motion_start span, update docs and config reference, and record the deferred follow-ups.

## Notes

[2026-11-17T22:36:28Z · sase-1tb.6] PROPOSED FOLLOW-UP: Streamed kitty-animation player (research Phase 3), gated on real-kitty rendering spike and demonstrated demand — see research wire-format rules

[2026-11-17T22:36:42Z · sase-1tb.6] PROPOSED FOLLOW-UP: In-TUI file-panel poster rider for video artifacts

[2026-11-17T22:36:48Z · sase-1tb.6] PROPOSED FOLLOW-UP: Persistent viewer pane or mpv IPC to avoid per-open motion spawn

[2026-11-17T22:36:54Z · sase-1tb.6] PROPOSED FOLLOW-UP: Gateway byte-range media route for remote video artifacts

[2026-11-17T22:58:50Z · sase-1tb.6--1] PROPOSED FOLLOW-UP: Pre-existing symvision failure — MemoryAuditRow in src/sase/memory/_read_log_query_facade.py reported unused; reproduces identically on clean base tree (verified via stash + just _lint-symvision), unrelated to motion-handoff phase

[2026-11-17T23:36:24Z · sase-1tb.6--1] PROPOSED FOLLOW-UP: Pre-existing check failures (all reproduce on clean base, none touched by this phase): TUI import footprint cap blown on base (11,865,563 vs 11,828,610; this phase adds only +5,419B in existing modules, zero new edges), KNOWN test_tracked_marker_mutation_sites_are_reviewed, KNOWN test_pipe_e2e default-pipe, FLAKY import-budget timing test; triage witness run b28e0afcb255e9bf15fc3adc4fca3f1d

[2026-11-17T23:36:42Z · sase-1tb.6--1] Motion backends verified: docs contract green after trimming video-preview section under 6000-word cap; fixed mpv doctor-test wording to new topology copy (tests/main/test_doctor_tools.py); artifact_file_viewer suite 189 passed incl 15 motion tests; full check run b28e0afcb255e9bf15fc3adc4fca3f1d shows only pre-existing KNOWN/FLAKY items (symvision MemoryAuditRow, import footprint cap blown on base, marker-mutation audit, pipe e2e) recorded as PROPOSED FOLLOW-UPs; no epic-symbols left

## Dependencies

- **Depends on:** [sase-1tb.5](sase-1tb.5.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1tb.7](sase-1tb.7.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tb.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tb.6.md) | [sase-1tb.6](sase-1tb.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4a6d3c5`](https://github.com/sase-org/sase/commit/4a6d3c51b352c61f9054b01546663f4a0a48c536) | feat(viewer): motion backends, native handoff, and muted in-pane audio | [sase-1tb.6](sase-1tb.6.md) | 2026-11-17 18:39:30 EST |

# Bead: sase-1ef.3 — Time band with playhead scrubber, explicit diff endpoints, and tombstone chrome

[Bead Pages](../README.md) / [sase-1ef](README.md) / sase-1ef.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v2.md) · **Assignee:** `sase-1ef.3` · **Size:** medium
**Created:** 2026-10-01 15:31:49 EDT · **Closed:** 2026-10-01 19:36:10 EDT
**Plan:** [202610/pager\_version\_clarity.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_version_clarity.md)

## Description

band: rebuild the time band around a playhead scrubber with labelled ends, absolute time, and the commit subject; show the compared range and both endpoints in the diff view; tint the band in the past; move the deletion notice out of the body and into chrome.

## Notes

[2026-10-01T23:36:10Z · sase-1ef.3] Band phase done and verified: playhead scrubber (render_scrubber, labelled v1/now ends, 2-cell slots <=12v else 1-cell, 60-cell bucketing) drives the timeline-first/meaning-second band with absolute dates, commit subjects, N newer + upstream markers and spec shedding order; diff view shows comparing vA->vB with delete/insert-toned endpoints and range-tinted track; past band uses band_past_tint via HistoryStyles in _update_time_band (signature carries view/diff/newer/tint/tombstone); model reads current/newest/dirty/view/diff/newer/tombstone from VersionMoment; deletion banner removed from body (exact last content) into tombstone chrome row. Tests: 27 band unit tests (scrubber matrix 1/2/12/13/25/260v, hidden/deleted, adjacent/split diff, tombstone, rename path, tint contrast), provider no-injected-line test, 118 chrome/gutter/moment/styles/diff/trail + 26 app-history tests green; ruff/mypy/symvision clean; goldens regenerated (timeband_diff-range + timeband_many-versions created, 30 updated incl. history_tombstone chrome) with 6 PNGs pixel-inspected; sase tool run check verdict pass (run 2e2a554b); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1ef.2](sase-1ef.2.md) ✓ · ⧖ 2026-10-01
- **Blocks:** [sase-1ef.5](sase-1ef.5.md) ◐ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ef.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ef.3/README.md) | [sase-1ef.3](sase-1ef.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cf0b8e0`](https://github.com/sase-org/sase/commit/cf0b8e02d93b83e7f7be164cb86ca3d34d5cb8b3) | feat(pager): rebuild time band around playhead scrubber | [sase-1ef.3](sase-1ef.3.md) | 2026-10-01 19:51:58 EDT |

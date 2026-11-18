# Bead: sase-1tb.7 — Cell-preview fallback for terminals without kitty graphics

[Bead Pages](../README.md) / [sase-1tb](README.md) / sase-1tb.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1di](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1di.md) · **Assignee:** `sase-1tb.7` · **Size:** small
**Created:** 2026-11-17 11:16:34 EST · **Closed:** 2026-11-17 19:24:07 EST
**Plan:** [202611/fast\_video\_artifact\_pane.md](https://github.com/sase-org/sase--plans/blob/main/202611/fast_video_artifact_pane.md)

## Description

non-kitty-fallback: detect kitty-graphics capability from the terminal name, using tmux's client_termname inside tmux. Otherwise render the current frame with the existing Unicode cell renderer plus metadata, and fall back the same way when kitten icat fails.

## Notes

[2026-11-18T00:11:51Z · sase-1tb.7] Phase work implemented; verify monitor njfcr4 (tool run 98aa1a2fb0943091966fcfa4d81a482e) owns final check. Closes when that check is green.

[2026-11-18T00:12:01Z · sase-1tb.7] Implemented kitty_graphics_capable (TERM kitty/ghostty or KITTY_WINDOW_ID outside tmux; bounded tmux display-message client_termname inside tmux; per-process cache) plus cell-preview fallback in run_video_inspect: hides storyboard, keeps status/footer with one-line banner, steps re-render cells, icat failure falls back the same way. Exports via graphics/__init__, viewer, _viewer_loop facade. Tests: new test_video_fallback.py (8 tests); 98 neighboring video tests green. Docs: #video-preview sentence added; page was at 5998/6000 budget so sentence shortened and ~14 words trimmed elsewhere to stay at 5998.

[2026-11-18T00:24:07Z · sase-1tb.7--1] Implemented kitty_graphics_capable + cell-preview fallback; 8 new tests green, 98 neighboring video tests green; just check (tool run 98aa1a2fb0943091966fcfa4d81a482e, monitor njfcr4) exit 0; sase bead epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1tb.6](sase-1tb.6.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tb.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tb.7.md) | [sase-1tb.7](sase-1tb.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f28da33`](https://github.com/sase-org/sase/commit/f28da33a13f55399cc6df2a8791d1658f9eb970d) | feat(ace): cell-preview fallback for terminals without kitty graphics | [sase-1tb.7](sase-1tb.7.md) | 2026-11-17 19:25:57 EST |

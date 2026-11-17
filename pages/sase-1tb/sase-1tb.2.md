# Bead: sase-1tb.2 — Trim the viewer child's startup tax

[Bead Pages](../README.md) / [sase-1tb](README.md) / sase-1tb.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1di](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1di.md) · **Assignee:** `sase-1tb.2` · **Size:** small
**Created:** 2026-11-17 11:16:33 EST · **Closed:** 2026-11-17 12:16:07 EST
**Plan:** [202611/fast\_video\_artifact\_pane.md](https://github.com/sase-org/sase--plans/blob/main/202611/fast_video_artifact_pane.md)

## Description

viewer-child-startup: pass the parent's resolved video config to the pane child through an env snapshot, lazy-import markdown_pdf, replace the clear subprocess with ANSI, add the child-side trace helper, and measure and fix kitten icat detection cost inside tmux.

## Notes

[2026-11-17T16:33:11Z · sase-1tb.2] Measured before/after for viewer-child-startup:

- Config snapshot: parent now passes SASE_ARTIFACT_VIEWER_VIDEO_CONFIG JSON via split-window -e, resolved with load_merged_artifact_video_playback_config() so a stale env never self-propagates. Child load_artifact_video_playback_config() parses the snapshot first and skips load_merged_config() on a valid v1 object (plan baseline for that reload: 0.42s).
- Import: python -X importtime -c "import sase.ace.tui.graphics.viewer" after lazy markdown_pdf is 0.131s cumulative (was 0.136s); sase.attachments.markdown_pdf is absent from sys.modules. sase.ace package __init__ is still ~0.090s; left it alone (optional, not a local low-risk win).
- kitten icat inside tmux (pty with TIOCSWINSZ 120x40 / 1200x800, TERM=xterm-kitty): detect mean 0.030s, stream 0.028s, default 0.028s. Detection did not add a wait when the terminal answered. Pane viewer still passes --transfer-mode=stream inside tmux so remote sessions cannot pick file/memory and cannot fall into the 10s --detection-timeout. kitten_icat_command() default argv is unchanged.
- clear_terminal() writes ESC [H ESC [2J ESC [3J and spawns no subprocess.
- Child spans artifact_viewer.child_ready / .first_visual go through the existing TUI JSONL sink when SASE_TUI_TRACE=1; parent forwards SASE_TUI_TRACE and SASE_TUI_TRACE_PATH via -e.

[2026-11-17T17:16:07Z · sase-1tb.2] Verified viewer-child-startup: env snapshot of merged video config via split-window -e, lazy markdown_pdf, ANSI clear, child_ready/first_visual traces, stream icat inside tmux. 90 artifact_file_viewer tests passed; sase tool run check 75fa00190c4a74690ed965bb50a51c0a green; no leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1tb.3](sase-1tb.3.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1tb.5](sase-1tb.5.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tb.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tb.2/README.md) | [sase-1tb.2](sase-1tb.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4878259`](https://github.com/sase-org/sase/commit/487825956afdd4eba04706367c563b5addea3723) | feat(tui): trim artifact viewer child startup tax | [sase-1tb.2](sase-1tb.2.md) | 2026-11-17 12:17:46 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tb.2][1] | Need current phase notes, status, and remaining work before close | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tb.2/README.md

<!-- sase:referenced-by:end -->

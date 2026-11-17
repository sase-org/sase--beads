# Bead: sase-1tb.3 — Move tmux split and decoration off the Textual UI thread

[Bead Pages](../README.md) / [sase-1tb](README.md) / sase-1tb.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1di](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1di.md) · **Assignee:** `sase-1tb.3` · **Size:** medium
**Created:** 2026-11-17 11:16:33 EST · **Closed:** 2026-11-17 13:40:14 EST
**Plan:** [202611/fast\_video\_artifact\_pane.md](https://github.com/sase-org/sase--plans/blob/main/202611/fast_video_artifact_pane.md)

## Description

async-pane-launch: launch the tmux split and pane decoration in a pump-free worker with an explicit launch context and bounded tmux timeouts. Show an opening state, show a VCS-materialization progress toast, and emit parent-side open spans correlated with the child.

## Notes

[2026-11-17T18:40:14Z · sase-1tb.3] Moved tmux split and pane decoration off the Textual UI thread via spawn_pump_free_task + asyncio.to_thread, with ArtifactViewerLaunchContext (no os.environ mutation), 2s tmux timeouts, opening/fetching toasts, in-flight guard, and parent open.select/.materialize/.split/.decorate spans. Verified with 66 targeted tests plus sase tool run check (0e392818dbbdda996f2d3ff6d361bc28).

## Dependencies

- **Depends on:** [sase-1tb.2](sase-1tb.2.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tb.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tb.3/README.md) | [sase-1tb.3](sase-1tb.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5b4e61b`](https://github.com/sase-org/sase/commit/5b4e61bfa7d256d0fb29317eb268782bbee7f42b) | feat(tui): launch artifact tmux panes off the UI thread | [sase-1tb.3](sase-1tb.3.md) | 2026-11-17 13:42:05 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tb.3][1] | Need the phase scope, design file, notes, and DECISIONS before finishing remaining work | 6 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tb.3/README.md

<!-- sase:referenced-by:end -->

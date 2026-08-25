# Bead: sase-tt.1 — Honest first-paint benchmarks for the Artifacts panes

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.1` · **Size:** small
**Created:** 2026-08-25 14:59:12 EDT · **Closed:** 2026-08-25 15:49:30 EDT
**Plan:** [202608/artifacts\_query\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)

## Description

bench: build a pane-level first-paint benchmark over a live-scale synthetic corpus and repair the agent-catalog bench, whose fixture structurally omits the two costs that actually dominate the real registry load.

## Notes

[2026-08-25T19:49:30Z · sase-tt.1] Auto-closed by `sase stitch create` after create_commit landed 4fcd56796 ("test(perf): add first-paint bench for artifacts pane and dedupe agent-catalog bench helpers"). No verification is implied by this note. Reopen with `sase bead open sase-tt.1`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Blocks:** [sase-tt.2](sase-tt.2.md) ◐ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.3](sase-tt.3.md) ◐ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.4](sase-tt.4.md) ◐ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.5](sase-tt.5.md) ◐ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.6](sase-tt.6.md) ◐ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.7](sase-tt.7.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.1/README.md) | [sase-tt.1](sase-tt.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4fcd567`](https://github.com/sase-org/sase/commit/4fcd56796af06c5d42611f9b94c2cc92ec8c3918) | test(perf): add first-paint bench for artifacts pane and dedupe agent-catalog bench helpers | [sase-tt.1](sase-tt.1.md) | 2026-08-25 15:46:55 EDT |

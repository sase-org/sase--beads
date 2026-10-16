# Bead: sase-1lh.5 — Harden tools/release\_watch so its bead close is guaranteed

[Bead Pages](../README.md) / [sase-1lh](README.md) / sase-1lh.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10q](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10q.md) · **Assignee:** `sase-1lh.5` · **Size:** medium
**Created:** 2026-10-16 13:00:20 EDT · **Closed:** 2026-10-16 13:33:01 EDT
**Plan:** [202610/v0\_18\_0\_green\_ci\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_green_ci_release.md)

## Description

watcher: make every exit path close the bead even under a process-group kill, and end the watch early on a stuck red Master Gate.

## Notes

[2026-10-16T17:32:44Z · sase-1lh.5] PROPOSED FOLLOW-UP: regenerate stale docs/reference/cli/* help output (docs-gen-check fails identically on clean base; argparse wrap drift from other merged CLI work)

[2026-10-16T17:33:01Z · sase-1lh.5] Watcher hardened per plan: STOPPED(18)/detached new-session closer on SIGTERM/SIGINT/SIGHUP with verdict written first; idempotent closes via bead read (ALREADY_CLOSED exit 0 at startup); MASTER_GATE_RED(17) after --max-red-gate-minutes (default 120, in-flight neutral) with one gh run rerun --failed per SHA for test-shard-only reds; fresh Full CI red budget (post-start runs only); -n/--no-dispatch observe-only mode; flushed/line-buffered state lines; docs Watching-a-release updated. Verified: 76/76 release-watch tests pass (incl. new SIGTERM+5s-group-SIGKILL subprocess proof that the detached closer still closes), just lint exit 0, just fix clean. sase tool run check fails only on pre-existing docs-gen-check CLI drift, reproduced identically on clean base (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1lh.6](sase-1lh.6.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.5/README.md) | [sase-1lh.5](sase-1lh.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`909d55d`](https://github.com/sase-org/sase/commit/909d55df5e948968c6c40e9dde5166d47b10433b) | feat(release-watch): harden watcher close guarantees and stuck-gate exit | [sase-1lh.5](sase-1lh.5.md) | 2026-10-16 13:34:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lh.5][1] | Need the phase scope and design file | 5 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.5/README.md

<!-- sase:referenced-by:end -->

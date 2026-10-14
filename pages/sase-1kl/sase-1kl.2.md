# Bead: sase-1kl.2 — Deterministic captures, then rebaseline the Artifacts-strip goldens

[Bead Pages](../README.md) / [sase-1kl](README.md) / sase-1kl.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.106](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.106.md) · **Assignee:** `sase-1kl.2` · **Size:** medium
**Created:** 2026-10-13 14:15:36 EDT · **Closed:** 2026-10-13 17:16:46 EDT
**Plan:** [202610/v0\_18\_0\_release\_unblock.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release_unblock.md)

## Description

visual-lane: fix the capture races and host differences behind 5 of the 57 drifted goldens, regenerate the rest for the intended retired-Agent Artifacts strip, and prove a clean full visual check under TZ=UTC.

## Notes

[2026-10-13T21:16:21Z · sase-1kl.2] PROPOSED FOLLOW-UP: Full-load 15s SVG-wait timeouts — tool_runs_session_rail times out identically on clean base (same digest e18ac6274c20); convert aged SVG-hammer waits to light app-state polls

[2026-10-13T21:16:26Z · sase-1kl.2] PROPOSED FOLLOW-UP: Visual drift-audit noise reproducing on base — renamed_generic_session_root, turns_gate scrollbar, archive_list durations, plus check import-budget failure; triage for land/release phase with Full CI as arbiter

[2026-10-13T21:16:31Z · sase-1kl.2] PROPOSED FOLLOW-UP: Full-load-only settled-state flakes — settled_monitor_lane_badge monitor state machine and turns_gate_90 cleanup count need semantic settle waits, not frame convergence

[2026-10-13T21:16:46Z · sase-1kl.2] visual-lane done: fixed Main-deck sink races behind main-0/main-1 flips (sync re-sync for digest-deduped placeholders + async availability refresh, sase-1a3 class) and top-bar pre-layout density; regen 55 goldens (53 Artifacts-strip + by_machine + auto_approve main-0-to-main-1), regen diffs pixel-verified to the intended rows. Proofs: full TZ=UTC fix-tui-screenshots check 1365 passed 0 failed (twice), tab-strip 4-file 27 passed, stale_host and by_machine 5x serial green, 12 unit/pin/retry scoped green, just fix clean, sase tool run check 55528 passed with 3 failures triaged (bounded-drain flake green on retry, import-budget fails identically on base, header-pin regression from resync-show fixed via storage-only delivery and green). Leftover full-load flakes and base-repro drift filed as 3 PROPOSED FOLLOW-UP notes; epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1kl.4](sase-1kl.4.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kl.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kl.2/README.md) | [sase-1kl.2](sase-1kl.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cf550a0`](https://github.com/sase-org/sase/commit/cf550a0e57065750c73bb9cafa7700039f18b868) | fix(ace-tui): fix Main-deck sink races and top-bar pre-layout density | [sase-1kl.2](sase-1kl.2.md) | 2026-10-13 17:18:39 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kl.2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kl.2/README.md

<!-- sase:referenced-by:end -->

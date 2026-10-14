# Bead: sase-1kx.5.1 — Repair the watcher edge cases and finish the clean visual proof

[Bead Pages](../README.md) / [sase-1kx.5](sase-1kx.5.md) / sase-1kx.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1kx.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.land.md) · **Assignee:** `sase-1kx.5.1` · **Size:** medium
**Created:** 2026-10-14 09:33:41 EDT · **Closed:** 2026-10-14 11:02:15 EDT
**Plan:** [202610/v0\_18\_0\_release\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release_finish.md)

## Description

remaining-fixes: fix the three watcher defects, await the requested core release, resolve the remaining visual mismatches, and verify the integrated tree.

## Notes

[2026-10-14T15:02:15Z · sase-1kx.5.1--3] Watcher remaining-fixes plus tests; TZ-independent goldens for agents_session_panel_turns_gate 90x40/120x40 (cleanup wait + MAIN overlay scrollbar hide), link_rail_agents_single_link 60x30, and plan_gate (90-col decision-id sentinel vs 120-col ask[:24]). Full TZ=UTC just fix-tui-screenshots --check clean: 1366 passed, created=0 updated=0 unchanged=1100 stale=0 (run fa10712a3a574a9ea60dc9b185618ba6). sase tool run check 933abe374ee28172dfa8b09d2c1bd597 succeeded (just check, triage pass). No leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1kx.5.2](sase-1kx.5.2.md) ✓ · ⧖ 2026-10-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kx.5.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.5.1.md) | [sase-1kx.5.1](sase-1kx.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`960f1e1`](https://github.com/sase-org/sase/commit/960f1e1b670a6993ef885506359f9b3166ae318b) | fix(release): close watcher edge cases and host-independent goldens | [sase-1kx.5.1](sase-1kx.5.1.md) | 2026-10-14 11:16:19 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kx.5.1--3][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.5.1.md

<!-- sase:referenced-by:end -->

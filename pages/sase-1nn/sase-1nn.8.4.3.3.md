# Bead: sase-1nn.8.4.3.3 — Repair the Full CI visual-test reds

[Bead Pages](../README.md) / [sase-1nn.8.4.3](sase-1nn.8.4.3.md) / sase-1nn.8.4.3.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13x](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13x.md) · **Size:** medium
**Created:** 2026-10-24 16:37:48 EDT · **Closed:** 2026-10-24 17:13:52 EDT
**Plan:** [202610/v0\_18\_1\_release\_unblock.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_unblock.md)

## Description

visual: find out why the stranded Beads PNG and any other drifting goldens differ on CI, make their renders deterministic, regenerate them after semantic review, and prove the full screenshot check is clean.

## Notes

[2026-10-24T20:59:24Z · sase-1nn.8.4.3.3] PROPOSED FOLLOW-UP: agents_weighted_runner_capacity_expanded_80x32 drifted 14077px once in Full CI 40101618059 at 02cd3b39b6, then passed in both 7b1b437558 runs (40108758095, 40109539212) and is check-clean at tip 3d70e0a81b — one-off with no owner bead, left as flake watch, golden untouched.

[2026-10-24T20:59:30Z · sase-1nn.8.4.3.3] PROPOSED FOLLOW-UP: local targeted check flagged test_agents_selected_row_png_snapshot unstable (passed on recapture) once at tip; never reported by CI visual-test jobs — local capture wobble only, no action.

[2026-10-24T21:13:48Z · sase-1nn.8.4.3.3--1] PROPOSED FOLLOW-UP: full visual check 3ae8e15eb4354f9e81e0eb82beb21731 clean with 5 local capture wobbles matched on recapture (clan_panel_swarm, clan_tree_collapsed, stranded_resolve_modal, plan_gate_maxcopy, history_past-frame_dark_60x30) — same class as note #2, no golden drift, flake watch only

[2026-10-24T21:13:52Z · sase-1nn.8.4.3.3--1] Full TZ=UTC just fix-tui-screenshots --check clean at tip (visual run 3ae8e15eb4354f9e81e0eb82beb21731: created=0 updated=0 unchanged=1119 stale=0, status clean, exit 0, monitor tool run 21d0c3596ce827bd4d86ddf5bc4ff210); regenerated artifacts_beads_stranded_120x40.png verified among unchanged (byte_equal, 0 changed pixels), sole modified file in git status; targeted two-zone proof plus lint+scoped tests passed this turn as tool run 12aaa88bb17634ab3fb695b2c0ab05cb; epic-symbols empty.

## Dependencies

- **Blocks:** [sase-1nn.8.4.3.4](sase-1nn.8.4.3.4.md) ✓ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.4.3.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.3.3.md) | [sase-1nn.8.4.3.3](sase-1nn.8.4.3.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5e79f64`](https://github.com/sase-org/sase/commit/5e79f6405f263f48fffc2e9f9f59ca34fa2ce23f) | fix(visual): regenerate stranded Beads golden and prove full screenshot check clean | [sase-1nn.8.4.3.3](sase-1nn.8.4.3.3.md) | 2026-10-24 17:14:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nn.8.4.3.3--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.3.3.md

<!-- sase:referenced-by:end -->

# Bead: sase-1nn.8.4.3.3 — Repair the Full CI visual-test reds

[Bead Pages](../README.md) / [sase-1nn.8.4.3](sase-1nn.8.4.3.md) / sase-1nn.8.4.3.3

**Status:** ◎ claimed · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13x](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13x.md) · **Assignee:** `sase-1nn.8.4.3.3--mon` · **Size:** medium
**Created:** 2026-10-24 16:37:48 EDT
**Plan:** [202610/v0\_18\_1\_release\_unblock.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_unblock.md)

## Description

visual: find out why the stranded Beads PNG and any other drifting goldens differ on CI, make their renders deterministic, regenerate them after semantic review, and prove the full screenshot check is clean.

## Notes

[2026-10-24T20:59:24Z · sase-1nn.8.4.3.3] PROPOSED FOLLOW-UP: agents_weighted_runner_capacity_expanded_80x32 drifted 14077px once in Full CI 40101618059 at 02cd3b39b6, then passed in both 7b1b437558 runs (40108758095, 40109539212) and is check-clean at tip 3d70e0a81b — one-off with no owner bead, left as flake watch, golden untouched.

[2026-10-24T20:59:30Z · sase-1nn.8.4.3.3] PROPOSED FOLLOW-UP: local targeted check flagged test_agents_selected_row_png_snapshot unstable (passed on recapture) once at tip; never reported by CI visual-test jobs — local capture wobble only, no action.

## Dependencies

- **Blocks:** [sase-1nn.8.4.3.4](sase-1nn.8.4.3.4.md) ◐ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.4.3.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.3.3.md) | [sase-1nn.8.4.3.3](sase-1nn.8.4.3.3.md) | 0 |

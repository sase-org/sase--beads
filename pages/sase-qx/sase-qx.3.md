# Bead: sase-qx.3 — Launch Control soft-disable workflow

[Bead Pages](../README.md) / [sase-qx](README.md) / sase-qx.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07o.md) · **Assignee:** `sase-qx.3` · **Size:** medium
**Created:** 2026-08-19 09:58:32 EDT · **Closed:** 2026-08-19 14:49:09 EDT
**Plan:** [202608/soft\_provider\_disables.md](https://github.com/sase-org/sase--plans/blob/main/202608/soft_provider_disables.md)

## Description

provider-ui: add the `s` soft-disable action and mode-aware rendering to Provider Routing, keep the current window when flipping mode, show sparing state in the Launch Control rows, top-bar pill, model picker, and `%model` completion, and document all of it.

## Notes

[2026-08-19T18:48:34Z · sase-qx.3--1] PROPOSED FOLLOW-UP: just check-full test-cost SIGKILL (exit 137) under host contention — not a phase assertion. Lint/mypy/symvision/validation/committed-plans were green; test-cost collected 34415 items, reached ~3%, then Killed while three other cost lanes plus visual/scoped/fast holders were live (host ~48Gi used / 28Gi swap). Phase unit tests 191 passed this turn; visual goldens already accepted (33). Land agent should re-run check-full on a quieter host before the combined tree lands.

[2026-08-19T18:49:09Z · sase-qx.3--1] User can soft-disable from Launch Control in two keypresses (s then a duration), flip hard/soft without losing the window (keep-current-window row on the other mode only), and see sparing state on Provider Routing rows/title, the top-bar pill (CLAUDE soft 1h; soft palette only when every disable is soft), the model picker (soft header, models still selectable), and %model completion (soft provenance). Selector sparing members keep the pool available count and a soft chip. Docs updated in ace.md and llms.md. Visual goldens accepted this session (just test-visual --sase-update-visual-snapshots; 33 passed, including the three new PNGs). Targeted unit tests 191 passed this turn. just check-full lint/mypy/symvision/validation/committed-plans were green; the cost lane then died with SIGKILL (exit 137) under host contention at ~3% of 34415 items — not a phase assertion failure; recorded as PROPOSED FOLLOW-UP. No --epic-symbol leftovers for this phase; parent still owns sase-qx(provider_routing_state).

[2026-08-19T18:53:29Z · sase-qx.3--1] User can soft-disable from Launch Control in two keypresses (s then a duration), flip hard/soft without losing the window (keep-current-window row on the other mode only), and see sparing state on Provider Routing rows/title, the top-bar pill, the model picker, and %model completion. Selector sparing members keep the pool available count and a soft chip. Docs updated in ace.md and llms.md. Visual goldens accepted this session (just test-visual --sase-update-visual-snapshots; 33 passed, including the three new PNGs). Targeted unit tests 191 passed. just check-full lint/mypy/symvision/validation/committed-plans were green; the cost lane then died with SIGKILL (exit 137) under host contention at ~3% of 34415 items — not a phase assertion failure; recorded as PROPOSED FOLLOW-UP. No --epic-symbol leftovers for this phase.

## Dependencies

- **Depends on:** [sase-qx.2](sase-qx.2.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qx.5](sase-qx.5.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qx.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-qx.3.md) | [sase-qx.3](sase-qx.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c8a0e71`](https://github.com/sase-org/sase/commit/c8a0e7184a4eb0961fe75afe82ce90962e45eded) | feat(ace): add Launch Control soft-disable workflow | [sase-qx.3](sase-qx.3.md) | 2026-08-19 14:54:31 EDT |

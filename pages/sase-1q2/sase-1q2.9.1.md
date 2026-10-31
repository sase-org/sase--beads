# Bead: sase-1q2.9.1 — Clear the footprint microbench, prompt-bar reveal, and any other blocking-lane red at the tip

[Bead Pages](../README.md) / [sase-1q2.9](sase-1q2.9.md) / sase-1q2.9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1q2.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q2.land.md) · **Assignee:** `sase-1q2.9.1` · **Size:** medium
**Created:** 2026-10-31 05:23:22 EDT · **Closed:** 2026-10-31 08:58:12 EDT
**Plan:** [202610/v0\_19\_0\_release\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_19_0_release_finish.md)

## Description

gate-reds: make Footprint bump() meet its 2 µs budget, measure it untraced, fix the hot-spare reveal subtitle race, then fix every other deterministic Master Gate or blocking Full CI red.

## Notes

[2026-10-31T12:57:57Z · sase-1q2.9.1--5] PROPOSED FOLLOW-UP: check flakes under 14-worker loaded full suite — test_blocked_render_is_bounded_and_leaves_the_request_queued (32.3s vs 5s bound, passes solo in 1.29s) and test_ctrl_x_wins_over_input_cut_and_works_from_every_field (pilot.pause timeout, triage FLAKY, passes solo); both in files untouched by this phase, both green in isolation on this tree

[2026-10-31T12:58:12Z · sase-1q2.9.1--5] bump: Master Gate baseline 3.380us (tip run 41201880902 shard test(4) still red at 2.949us on unoptimized code; prior untraced athena ~1.23us) -> 0.501us local untraced best-of-5x5000 after cache+lock optimization. Stress: 20/20 serial microbench, 3/3 parallel footprint file, coverage 1 passed, combined loaded footprint+ACE 18625 passed, 20/20 subtitle parity both params, 3x full ACE TUI 18624 green each, post-width-change repeat 20/20 parity + 3x ACE green, 14/14 footprint after symvision fix. Reveal parity test_reveal_matches_fresh_home green. Lanes: Master Gate tip only red is bump (fixed here); Full CI 41174188852 reds (bump+reveal fixed here; cli_names/format pass on this tree; visual+lint need owner triage); fresh Full CI 41202104560 in progress. check: all lint gates pass, 59363 passed with 2 load flakes (bounded_drain 32s timing + ctrl_x pilot timeout, both solo-green, filed as follow-up). 10 files changed, just fix clean.

## Dependencies

- **Blocks:** [sase-1q2.9.3](sase-1q2.9.3.md) ◐ · ⧖ 2026-10-31

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q2.9.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q2.9.1.md) | [sase-1q2.9.1](sase-1q2.9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ddefc62`](https://github.com/sase-org/sase/commit/ddefc625e001ae255596f77a6461abb642f3929e) | perf(tui): keep footprint bump() under its 2us budget and fix hot-spare reveal subtitle race | [sase-1q2.9.1](sase-1q2.9.1.md) | 2026-10-31 09:00:25 EDT |

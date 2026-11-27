# Bead: sase-1vn.2 — Green, meaningful test-cost budgets

[Bead Pages](../README.md) / [sase-1vn](README.md) / sase-1vn.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1h5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1h5.md) · **Assignee:** `sase-1vn.2` · **Size:** large
**Created:** 2026-11-27 10:21:03 EST · **Closed:** 2026-11-27 16:28:58 EST
**Plan:** [202611/backlog\_epic\_1.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_1.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:0bee5068b45f2a8d14dd6fc1 | attached via sase artifact create --bead |
| related | file:explicit:0c6bf85783f13300e8d3c47c | attached via sase artifact create --bead |
| related | file:explicit:1a88240988579736c6140252 | attached via sase artifact create --bead |
| related | file:explicit:1fa482f4cf347ac59b28ab35 | attached via sase artifact create --bead |
| related | file:explicit:81365da9fcfee7f81c0cfd0d | attached via sase artifact create --bead |
| related | file:explicit:f2f774fd30fcf4bccf90defa | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

test-cost: make just test-cost, check-full, and the CI Telemetry test-cost job green and meaningful on master again, per the cost_budgets decision (sase-j0).

## Notes

[2026-11-27T21:28:58Z · sase-1vn.2--2] CHECK-FULL VERIFICATION AND CALIBRATION (2026-11-27)

The new isolated full-run evidence is attached: file:explicit:0c6bf85783f13300e8d3c47c (4,301,960-byte raw recording) and file:explicit:1fa482f4cf347ac59b28ab35 (complete 144,447-byte monitor log). Monitor 62r1026bwztg ran the exact four-worker `just check-full` command from 19:13:59Z to 21:00:43Z and exited 1 after the complete pytest lane. It selected 63,822 fast-suite nodes over 5,847 files. All four workers reported; their per-worker node totals sum to 63,822. No worker crashed or stopped early. No ad-hoc paths, shards, `-k`, or non-default marker selection were used; the default fast lane excludes slow and visual tests by design.

The global leak detector reported four ACE tests poisoning `sase.config.core._live_config_token_refresh_threads`; the baseline independently confirmed `tests/ace/tui/test_agent_jump_clan_members.py::test_real_app_named_agent_jump_expands_collapsed_clan` on the same global. Existing owner `sase-1vg` remains open and covers this signature. `check-full` stopped in test-cost before visual snapshots; no visual report or PNG golden change was produced.

The recording replay initially found one local hard miss: collection CPU 53.562 seconds per worker exceeded the old 51.25 effective limit. CI replay passed. The isolated `--suggest` output recommends 51.0 using `round_up_nice(53.562 / (0.85 * 1.25))`; that committed hard limit leaves 16.0% sample headroom under its 63.75 effective allowance. After the update, both local and CI replays pass. Advisory wall overages were left advisory. Compared with the earlier same-day 4-worker sample, total file CPU rose 5.1%; per-cause CPU changes were 2.7-8.8%, and the largest current file was 1.88% of total CPU, so the measurements support suite-wide growth without a named per-file regression. Collection CPU has no per-file attribution.

Focused budget, runner, and Telemetry workflow contracts passed (93 tests). `sase tool run check` 533ceda265c79af4d7f890c0177218bd passed, including all static gates and scoped tests. `sase bead epic-symbols sase-1vn.2` returned no entries. Closing this phase with the independently tracked leak-gate exception preserved above; the parent epic remains open.

## Dependencies

- **Depends on:** [sase-1vn.1](sase-1vn.1.md) ✓ · ⧖ 2026-11-27
- **Blocks:** [sase-1vn.3](sase-1vn.3.md) ◐ · ⧖ 2026-11-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vn.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.2.md) | [sase-1vn.2](sase-1vn.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1b46158`](https://github.com/sase-org/sase/commit/1b461588eb33d6ce70f0c4414ce3fcd483e8f905) | test(test-cost): rebaseline suite budgets and retain telemetry records | [sase-1vn.2](sase-1vn.2.md) | 2026-11-27 16:31:31 EST |

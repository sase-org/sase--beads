# Bead: sase-17x.13.10.5 — Tip marker write, restored-block append, and history counts

[Bead Pages](../README.md) / [sase-17x.13.10](sase-17x.13.10.md) / sase-17x.13.10.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.13.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.land.md) · **Assignee:** `sase-17x.13.10.5` · **Size:** small
**Created:** 2026-09-25 08:41:46 EDT · **Closed:** 2026-09-25 11:45:30 EDT
**Plan:** [202609/command\_line\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_gaps.md)

## Description

ui-thread-state: move the palette-tip marker write off the loop. Append restored blocks on the UI thread only. Remember each run once in memory. Add the writes-chip and off-screen-tail pilot tests.

## Notes

[2026-09-25T15:45:04Z · sase-17x.13.10.5--1] PROPOSED FOLLOW-UP: flaky full-suite failures pass on rerun — dispatch hello timeout, pager y-then-label, palette-tip off-loop timing

[2026-09-25T15:45:30Z · sase-17x.13.10.5--1] tip marker write off loop, restored-block append on UI thread, per-run history counts with writes-chip and off-screen-tail pilot tests; command_line suite 203 passed, full check 47369 passed with 2 unrelated flakes (dispatch gateway, pager) that pass on rerun

## Dependencies

- **Depends on:** [sase-17x.13.10.2](sase-17x.13.10.2.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-17x.13.10.6](sase-17x.13.10.6.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.10.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.10.5.md) | [sase-17x.13.10.5](sase-17x.13.10.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ea25ee2`](https://github.com/sase-org/sase/commit/ea25ee2bf78796f9850c8164b71ff863b4162d8c) | fix(command-line): move tip marker write off loop, append restored blocks on UI thread (sase-17x.13.10.5) | [sase-17x.13.10.5](sase-17x.13.10.5.md) | 2026-09-25 11:47:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.13.10.5--1][1] | verify phase scope before close | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.10.5.md

<!-- sase:referenced-by:end -->

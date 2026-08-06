# Bead: sase-gg.3 — Make the rapid-navigation detail test drive the debouncer deterministically

[Bead Pages](../README.md) / [sase-gg](README.md) / sase-gg.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.u6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.u6/README.md) · **Assignee:** `sase-gg.3` · **Size:** small
**Created:** 2026-08-06 12:26:34 EDT · **Closed:** 2026-08-06 12:37:44 EDT
**Plan:** [202608/ci\_green\_restore.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_green_restore.md)

## Description

detailrace: stop assuming two keypresses land inside the 150 ms debounce window; control the timer the way the existing debouncer tests do and assert on the coalesced result.

## Notes

[2026-08-06T16:37:44Z · sase-gg.3] Rewrote test_rapid_navigation_loads_only_the_final_detail to intercept AceApp.set_timer instead of racing the 150ms debounce window: after two rapid j presses, calls==[] proves no timer fired yet (row-1 never loaded), then firing the captured callback manually yields calls==[rows[2].id]. Verified: pytest on the file passes (8/8), just check passes (all lint gates + scoped tests green).

[2026-08-06T16:38:27Z · sase-gg.3] Rewrote test_rapid_navigation_loads_only_the_final_detail to intercept AceApp.set_timer instead of racing the 150ms debounce window; verified pytest 8/8 pass and just check green.

## Dependencies

- **Blocks:** [sase-gg.5](sase-gg.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gg.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gg.3/README.md) | [sase-gg.3](sase-gg.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7a5a40b`](https://github.com/sase-org/sase/commit/7a5a40b14a04955052275c9d3e2afd4965278dac) | test(ace): make rapid-navigation detail test drive the debouncer deterministically | [sase-gg.3](sase-gg.3.md) | 2026-08-06 12:39:03 EDT |

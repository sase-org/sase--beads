# Bead: sase-17x.13.2 — Fix call\_from\_thread misuse on the app loop

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.2` · **Size:** small
**Created:** 2026-09-24 20:28:41 EDT · **Closed:** 2026-09-24 21:03:10 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

worker-hops: stop calling `call_from_thread` from coroutines that already run on the app loop. This fixes the `v` pager crash on an unloaded tail and the popup that never leaves `indexing commands…`. Sweep the package for the same pattern and add pilot tests on the real paths.

## Notes

[2026-09-25T01:02:42Z · sase-17x.13.2] PROPOSED FOLLOW-UP: just check is blocked by two pre-existing mypy errors in untouched tools/sase_core_wheel_cache (_identity_lock contextmanager annotation and acquired_lock annotation); targeted command-line pilots pass.

[2026-09-25T01:03:10Z · sase-17x.13.2] Verified the two new real-path pilots: v loads an unloaded tail and opens PagerScreen without WorkerFailed; grammar readiness clears the indexing popup/hint without a keystroke. Ran just fix and targeted tests via sase tool run (61865ed32de35be2bbd97bc0db22760c). sase tool run check (7e6322a6df92786e98fb18ddb73dd6c1) reached pre-existing mypy errors in untouched tools/sase_core_wheel_cache, recorded as a proposed follow-up.

## Dependencies

- **Blocks:** [sase-17x.13.3](sase-17x.13.3.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.2/README.md) | [sase-17x.13.2](sase-17x.13.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7484c50`](https://github.com/sase-org/sase/commit/7484c50abb1bd9c87897d5b0ae4b164da941f242) | fix(tui): avoid app-loop worker hops | [sase-17x.13.2](sase-17x.13.2.md) | 2026-09-24 21:04:52 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.13.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.2/README.md

<!-- sase:referenced-by:end -->

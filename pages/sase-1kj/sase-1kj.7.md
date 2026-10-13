# Bead: sase-1kj.7 — Make startup cliffs diagnosable from telemetry

[Bead Pages](../README.md) / [sase-1kj](README.md) / sase-1kj.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.102](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.102.md) · **Assignee:** `sase-1kj.7` · **Size:** small
**Created:** 2026-10-13 11:47:19 EDT · **Closed:** 2026-10-13 18:17:38 EDT
**Plan:** [202610/apollo\_tui\_startup.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_tui_startup.md)

## Description

startup-telemetry: always-on loader disk substage timings, plus release reason and time, host load, and relation-index build counts on tui_startup rows.

## Notes

[2026-10-13T22:17:30Z · sase-1kj.7--1] PROPOSED FOLLOW-UP: test_tui_app_import_stays_under_startup_budget fails at 3520 modules vs 3513 cap identically on clean HEAD (bda93bab64) with +0 from this phase (tools/tui_import_closure --diff); needs an owner to attribute/defer the 7-module drift or ratchet the cap

[2026-10-13T22:17:38Z · sase-1kj.7--1] startup-telemetry done: always-on disk substage timings (dismissed_snapshot/index/decode/provider/projections) on slow-loader rows, plus deferred_release_reason/time, load1/cpu_count, relation-index build count, auto-refresh ticks on tui_startup rows; epic-symbol row consumed from Justfile. Verified: 22 passed across test_agent_loader_phase5_wiring, test_startup_telemetry, test_startup_observability; fixed viewport-query test for new substages kwarg; ruff check+format clean. Pre-existing import-budget failure (3520 vs 3513, +0 from this phase, fails on clean HEAD) recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1kj.3](sase-1kj.3.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1kj.5](sase-1kj.5.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1kj.6](sase-1kj.6.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.7.md) | [sase-1kj.7](sase-1kj.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3c69bf5`](https://github.com/sase-org/sase/commit/3c69bf5a976ab97154a63a317393519c6616a338) | feat(tui): add startup telemetry and agent loader observability | [sase-1kj.7](sase-1kj.7.md) | 2026-10-13 18:19:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kj.7--1][1] | Need phase scope and design file | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.7.md

<!-- sase:referenced-by:end -->

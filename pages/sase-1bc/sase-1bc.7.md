# Bead: sase-1bc.7 — The beautiful tab strip

[Bead Pages](../README.md) / [sase-1bc](README.md) / sase-1bc.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0t4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0t4.md) · **Assignee:** `sase-1bc.7` · **Size:** large
**Created:** 2026-09-27 10:57:10 EDT · **Closed:** 2026-09-28 12:24:21 EDT
**Plan:** [202609/agents\_dynamic\_tabs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_dynamic_tabs.md)

## Description

tab-strip: build AgentTabStrip in #agents-header with accent labels, the active pill, count and attention badges, tiers, an overflow window with a tab picker, tooltips, jump hints, arrival dots, the emptied-tab latch, three-cause empty states, and golden coverage.

## Notes

[2026-09-28T16:24:21Z · sase-1bc.7--3] AgentTabStrip landed: descriptors + strip widget with accent labels, glyph, active pill, counts, S/F/U badges, N+ overflow, tiers + active-centered overflow window with picker entry points, searchable picker rows, apostrophe jump-hint integration, arrival dots, emptied-tab latch, three empty causes. Verified: 25 behavior tests pass, 9 PNG goldens unchanged via just test-visual, mypy + symvision clean, just fix clean. Full just check exits 1 only on 14 KNOWN + 1 FLAKY triaged failures (verdict no_new_failures); sase bead epic-symbols sase-1bc.7 is empty.

## Dependencies

- **Depends on:** [sase-1bc.6](sase-1bc.6.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.8](sase-1bc.8.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.9](sase-1bc.9.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.7.md) | [sase-1bc.7](sase-1bc.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`77438b4`](https://github.com/sase-org/sase/commit/77438b4ef1161a994983a3e2ced3bae395a5aa64) | feat(ace): complete the Agents tab strip (sase-1bc.7) | [sase-1bc.7](sase-1bc.7.md) | 2026-09-28 12:58:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bc.7--3][1] | verify phase completion before close | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.7.md

<!-- sase:referenced-by:end -->

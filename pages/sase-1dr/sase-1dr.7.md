# Bead: sase-1dr.7 — Time band chrome, sparkline, and honest states

[Bead Pages](../README.md) / [sase-1dr](README.md) / sase-1dr.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3o.md) · **Assignee:** `sase-1dr.7` · **Size:** medium
**Created:** 2026-09-30 19:09:28 EDT · **Closed:** 2026-10-01 08:39:53 EDT
**Plan:** [202609/memory\_history.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md)

## Description

time-band: add the time band. At now it is a one-row life strip; in the past it has two rows, a meaning row and a sparkline time row. Its provenance items are label targets. Add the instruction-file cause row, alias and diverged chips, honest state labels (untracked, ignored, no VCS, shallow, template, indexing, unavailable), and the upstream-ahead marker. Degrade by height and width together with the trail band. Add visual goldens.

## Notes

[2026-10-01T12:39:09Z · sase-1dr.7--1] PROPOSED FOLLOW-UP: just-check NEW failure tests/test_bead/test_show_images.py::test_parser_help_covers_images_and_open reproduces identically on clean base (expects -i/--images, parser now has -i {auto,cells,kitty,never}); untouched by time-band phase

[2026-10-01T12:39:26Z · sase-1dr.7--1] PROPOSED FOLLOW-UP: just-check NEW failure tests/completion/test_kind_coverage.py::test_every_value_slot_is_kinded_choiced_or_hinted reproduces identically on clean base (uncaptioned slot memory/history:at from committed sase-1dr.6, untouched by time-band phase)

[2026-10-01T12:39:53Z · sase-1dr.7--1] Time-band phase verified: 17 time-band unit tests pass, 18 PNG goldens pass, tests/pager+tests/memory 662 passed; epic-symbols clean. Full just check exit 1 only from 2 NEW failures in untouched files (bead show-images help, completion kind coverage memory/history:at), both reproduced identically on clean base and recorded as PROPOSED FOLLOW-UPs.

## Dependencies

- **Blocks:** [sase-1dr.11](sase-1dr.11.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dr.12](sase-1dr.12.md) ◐ · ⧖ 2026-09-30
- **Depends on:** [sase-1dr.6](sase-1dr.6.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.7.md) | [sase-1dr.7](sase-1dr.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3819d25`](https://github.com/sase-org/sase/commit/3819d254b3fe669eb2afcf7b4f64d04d1e94a248) | feat(sase-1dr.7): pager time band with sparkline, honest states, and PNG goldens | [sase-1dr.7](sase-1dr.7.md) | 2026-10-01 09:02:52 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dr.7--1][1] | Need phase scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.7.md

<!-- sase:referenced-by:end -->

# Bead: sase-1tz.1.1.4 — Represent unmeasured disk owners as unknown, never 0 B complete

[Bead Pages](../README.md) / [sase-1tz.1.1](sase-1tz.1.1.md) / sase-1tz.1.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) · **Assignee:** `sase-1tz.1.1.4` · **Size:** medium
**Created:** 2026-11-19 07:28:41 EST · **Closed:** 2026-11-19 09:09:39 EST
**Plan:** [202611/outage\_disk\_attribution\_and\_held\_workspaces.md](https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md)

## Description

unknown_sizes: the tree sizer returns measured, lower-bound, or unmeasured results. The sase-core disk-inventory wire moves to v2 with a per-row size state, unmeasured-owner reporting, and lower-bound totals. sase disk list renders unknown sizes honestly, and the pin moves.

## Notes

[2026-11-19T14:09:39Z · sase-1tz.1.1.4] unknown_sizes: BoundedTreeSizer returns measured/lower_bound/unmeasured; disk-inventory wire v2 with size_state, unmeasured_owners, totals_are_lower_bound; sase disk list renders unmeasured/\u2265X; unattributed residual names unmeasured owners. Verified sase-core sase tool run check (4e97915911c7da4dc542c97ef0defa5e) and sase sase tool run check (6a5fc50c9dc9970c1cbf4a9c5fbcf0bb); 39 targeted Python tests plus 15 sase_core disk_ + 2 sase_core_py disk_inventory tests.

## Dependencies

- **Blocks:** [sase-1tz.1.1.5](sase-1tz.1.1.5.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.1.1.6](sase-1tz.1.1.6.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.4/README.md) | [sase-1tz.1.1.4](sase-1tz.1.1.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@eabe416`](https://github.com/sase-org/sase-core/commit/eabe416cb5691876e3fd275e40769fcfbd18788d) | feat!: bump disk-inventory wire to v2 with per-row size state | [sase-1tz.1.1.4](sase-1tz.1.1.4.md) | 2026-11-19 09:10:50 EST |
| sase | [`6ee5f85`](https://github.com/sase-org/sase/commit/6ee5f8560caa8ec689349a3b5767954e5d99e4d6) | feat(disk): render unmeasured owners instead of 0 B complete | [sase-1tz.1.1.4](sase-1tz.1.1.4.md) | 2026-11-19 09:12:00 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.1.1.4][1] | Need full issue JSON for notes, decisions, design | 5 |
| read-by | [agent:sase-1tz.1.1.6][2] | Need unknown_sizes landed work this phase depends on | 1 |
| read-by | [agent:sase-1tz.1.1.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.4/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.6/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.land/README.md

<!-- sase:referenced-by:end -->

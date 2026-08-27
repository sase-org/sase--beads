# Bead: sase-ug.6 — The Link Rail, read-only

[Bead Pages](../README.md) / [sase-ug](README.md) / sase-ug.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eh.md) · **Assignee:** `sase-ug.6` · **Size:** medium
**Created:** 2026-08-26 14:48:27 EDT · **Closed:** 2026-08-26 22:21:03 EDT
**Plan:** [202608/link\_rail\_every\_tab.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_rail_every_tab.md)

## Description

rail: mount the one-line, app-owned rail above the footer on every tab, with the chip anatomy, stable ordering, degradation ladder, and the invisibility contract.

## Notes

[2026-08-27T02:21:03Z · sase-ug.6] Implemented link_rail beta flag, mounted the read-only LinkRail above the footer, refreshed it from an off-pump cached link index, and covered no-link, single, multi, collapsed projected, missing, chop, and flag-off follow-availability cases. Verified targeted pytest for link rail/link index/key resolution and just check pass; just check escalated to the full suite because of src-data-asset. Verified sase bead epic-symbols sase-ug.6 reports no entries.

## Dependencies

- **Depends on:** [sase-ug.5](sase-ug.5.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ug.7](sase-ug.7.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ug.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ug.6/README.md) | [sase-ug.6](sase-ug.6.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`48e019a`](https://github.com/sase-org/sase/commit/48e019af82f279fc51d53d0e1f1ec51123bebd80) | feat(ace): add read-only link rail | [sase-ug.6](sase-ug.6.md) | 2026-08-26 22:22:44 EDT |
| sase--agents | [`sase--agents@b438c6d`](https://github.com/sase-org/sase--agents/commit/b438c6dea33ab4a04d4800ef29acf6b501c24333) | chore(agents): archive link rail prompt | [sase-ug.6](sase-ug.6.md) | 2026-08-26 22:25:24 EDT |

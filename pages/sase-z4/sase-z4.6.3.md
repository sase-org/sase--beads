# Bead: sase-z4.6.3 — Correct queue projection and integrate weighted fleet rows

[Bead Pages](../README.md) / [sase-z4.6](sase-z4.6.md) / sase-z4.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.land.md) · **Assignee:** `sase-z4.6.3` · **Size:** medium
**Created:** 2026-09-10 08:15:42 EDT · **Closed:** 2026-09-10 11:38:53 EDT
**Plan:** [202609/weighted\_capacity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_landing_repairs.md)

## Description

capacity-presentation: project global local claims before display transformations, include serial waiters, consume shared parked ordering, carry remote weight metadata, and finish capacity labels and visual acceptance.

## Notes

[2026-09-10T15:38:53Z · sase-z4.6.3] Implemented weighted capacity display repairs; verified focused Python suite (150 passed), targeted visual snapshots (3 passed with PNG inspection), Rust fleet/core binding tests, cargo fmt --all --check, and just check rerun green after one flaky full-suite attempt passed direct rerun.

## Dependencies

- **Depends on:** [sase-z4.6.2](sase-z4.6.2.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-z4.6.4](sase-z4.6.4.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.6.3/README.md) | [sase-z4.6.3](sase-z4.6.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cceed09`](https://github.com/sase-org/sase/commit/cceed09a993f4395f045310f72ca6f25b14174c9) | fix(ace): display weighted runner capacity from source rows | [sase-z4.6.3](sase-z4.6.3.md) | 2026-09-10 11:40:27 EDT |
| sase-core | [`sase-core@8e491c3`](https://github.com/sase-org/sase-core/commit/8e491c337cafd43c44d1d34278fe16d64e069811) | feat(fleet): expose queue weight metadata | [sase-z4.6.3](sase-z4.6.3.md) | 2026-09-10 11:43:37 EDT |

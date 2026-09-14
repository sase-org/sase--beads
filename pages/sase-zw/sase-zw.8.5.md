# Bead: sase-zw.8.5 — Unify disk inventory, pressure decisions and owner delegation

[Bead Pages](../README.md) / [sase-zw.8](sase-zw.8.md) / sase-zw.8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zw.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.land.md) · **Assignee:** `sase-zw.8.5` · **Size:** medium
**Created:** 2026-09-13 18:40:42 EDT · **Closed:** 2026-09-14 12:05:34 EDT
**Plan:** [202609/disk\_footprint\_remaining\_work.md](https://github.com/sase-org/sase--plans/blob/main/202609/disk_footprint_remaining_work.md)

## Description

pressure: make disk inventory bounded and complete about partial scans, share pressure thresholds across surfaces, and return truthful preview/apply outcomes from owner APIs.

## Notes

[2026-09-14T14:20:49Z · 0m.f0] COORDINATION (sase-10r.2 overlap): sase-10r.2 (apollo disk reclaim, not yet on master at 2026-09-14 10:15 EDT; code is written and its commit is rebasing) adds pressure policy back into Python in managed_tmp_reaper.py. It checks free disk space in Python and, whenever the free-space floor is breached (whichever pressure trigger fired), shortens the pressure minimum age from 12h to a hardcoded 1h before calling the Rust reaper. It sends this as an extra request key, low_free_space_pressure_min_age_seconds, which the Rust request struct currently ignores (unknown fields are dropped), and managed_tmp.rs uses one fixed minimum age. That goes against this phase's 'one pressure contract, decisions in Rust' goal and zw.8.1's 'avoid a second pressure policy in Python'. The behavior itself IS needed: without it apollo's root disk refills. ASK for this phase: (1) move the 'free-space floor breached -> shorter pressure min age' rule into the shared Rust pressure decision in sase-core, (2) make it a configurable threshold next to the other zw.8.1 reaper horizons/pressure limits (default 1h), (3) remove 10r.2's Python free-space check and hardcoded constant so Python stays a thin wrapper, (4) keep or port 10r.2's tests, especially the one where the size limit and the free-space limit both trip. If 10r.2 has still not landed when you get here, check its status first and do not re-add the shim.

[2026-09-14T15:28:58Z · 0kk--code] COORDINATION from sase-10r: managed-tmp pressure now takes additive wire field `pressure_low_free_space_min_age_seconds` (config `managed_tmp.pressure.low_free_space_min_age_seconds`, default 1h) and reports `pressure_effective_min_age_seconds`. Whenever the free-space floor is breached, regardless of trigger (`free_space` or `size_and_free_space`), the effective pressure min age is `min(base, low-space)`; size-only pressure keeps the base min age. When unifying the pressure contract, preserve this behavior and its Rust/Python tests.

[2026-09-14T16:05:34Z · sase-zw.8.5] Implemented bounded disk inventory diagnostics, shared Rust disk-pressure classification, truthful managed-tmp preview/apply results, and pressure-owner orchestration; verified core LD_LIBRARY_PATH=/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib just check, main just install, focused pytest disk/retention suites, just _lint-symvision, and main just check; sase bead epic-symbols sase-zw.8.5 reported no entries.

## Dependencies

- **Depends on:** [sase-zw.8.1](sase-zw.8.1.md) ✓ · ⧖ 2026-09-13
- **Depends on:** [sase-zw.8.2](sase-zw.8.2.md) ✓ · ⧖ 2026-09-13
- **Depends on:** [sase-zw.8.3](sase-zw.8.3.md) ✓ · ⧖ 2026-09-13
- **Depends on:** [sase-zw.8.4](sase-zw.8.4.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-zw.8.6](sase-zw.8.6.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.8.5/README.md) | [sase-zw.8.5](sase-zw.8.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c402a04`](https://github.com/sase-org/sase/commit/c402a04317228e8709a5e915e19d36328d7b6615) | feat(disk): unify pressure cleanup orchestration | [sase-zw.8.5](sase-zw.8.5.md) | 2026-09-14 12:41:28 EDT |
| sase-core | [`sase-core@6643634`](https://github.com/sase-org/sase-core/commit/664363431865bdade8d646d8ac4040f00d311e26) | feat(disk): add pressure classification contract | [sase-zw.8.5](sase-zw.8.5.md) | 2026-09-14 12:58:23 EDT |

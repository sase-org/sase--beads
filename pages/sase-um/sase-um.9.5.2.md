# Bead: sase-um.9.5.2 — Bring successful Master Gate runs and the trailing median inside eight minutes

[Bead Pages](../README.md) / [sase-um.9.5](sase-um.9.5.md) / sase-um.9.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-um.9.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.9.land.md) · **Assignee:** `sase-um.9.5.2` · **Size:** medium
**Created:** 2026-08-28 20:17:49 EDT · **Closed:** 2026-08-28 20:59:47 EDT
**Plan:** [202608/finish\_release\_gate\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_release_gate_landing.md)

## Description

gatebudget: measure warm successful eight-shard runs and apply only the next proven critical-path lever needed to meet the live reliability, wall-time, and job-minute bounds.

## Notes

[2026-08-29T00:59:47Z · sase-um.9.5.2] Measured live Master Gate before the lever at 33 success / 16 failure / 1 cancelled over trailing 50 with 9.17m median; warm success 33217065947 was 11.62m and cache-miss success 33221794673 was 13.50m. Switched Master Gate and non-visual fast lanes off install-visual, ignored visual test dirs before collection, and verified focused workflow/shard/runner suite (221 passed), no-Pillow fast collect-only probe (38091/38103 collected with PIL blocked), sase bead epic-symbols (no entries), and just check.

## Dependencies

- **Blocks:** [sase-um.9.5.3](sase-um.9.5.3.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.9.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.9.5.2/README.md) | [sase-um.9.5.2](sase-um.9.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a97cabe`](https://github.com/sase-org/sase/commit/a97cabe3a2f4dd2186ee3775b85b57244efe3ef6) | perf(ci): trim Master Gate fast setup | [sase-um.9.5.2](sase-um.9.5.2.md) | 2026-08-28 21:01:09 EDT |

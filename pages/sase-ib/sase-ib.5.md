# Bead: sase-ib.5 — Shrink worker memory and collection cost

[Bead Pages](../README.md) / [sase-ib](README.md) / sase-ib.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wk/README.md) · **Assignee:** `sase-ib.5` · **Size:** medium
**Created:** 2026-08-09 10:32:11 EDT · **Closed:** 2026-08-09 13:06:50 EDT
**Plan:** [202608/fast\_test\_suite\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_test_suite_1.md)

## Description

footprint: reduce the per-worker collection time and the resident memory each xdist worker holds and grows, which is what currently caps how many workers the host can afford.

## Notes

[2026-08-09T17:06:50Z · sase-ib.5] Verified focused tests (26 passed), final cost record /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260809T164811Z-3964960.json: collection 12.399s, peak worker RSS 500632 KiB, RSS curve start=144292/post_collection=500632/median=500632/peak=500632 KiB, samples=3; just check passed.

[2026-08-09T17:08:09Z · sase-ib.5] Verified focused tests pass (26 passed), collect-only cost lane collection 12.399s with peak worker RSS 500632 KiB and RSS curve recorded, and just check passed.

## Dependencies

- **Depends on:** [sase-ib.1](sase-ib.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.6](sase-ib.6.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.7](sase-ib.7.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ib.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ib.5/README.md) | [sase-ib.5](sase-ib.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`35d2d51`](https://github.com/sase-org/sase/commit/35d2d51f9a84d02c75eed244f39e867853520836) | perf: reduce fast test collection footprint | [sase-ib.5](sase-ib.5.md) | 2026-08-09 13:09:23 EDT |

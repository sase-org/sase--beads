# Bead: sase-1sl.2 — Ratchet the core pin and re-measure the scan on the real archive

[Bead Pages](../README.md) / [sase-1sl](README.md) / sase-1sl.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1c0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1c0.md) · **Assignee:** `sase-1sl.2` · **Size:** small
**Created:** 2026-11-12 16:45:04 EST · **Closed:** 2026-11-13 01:20:32 EST
**Plan:** [202611/capacity\_scan\_tui\_runaway.md](https://github.com/sase-org/sase--plans/blob/main/202611/capacity_scan_tui_runaway.md)

## Description

sase-adopt-pin: move sase-core-revision.txt past the core commit, adopt any new scan option in runner_slots/_scan.py, and re-measure cold/warm capacity scans and runner-cache behavior on athena against the 22.9 s baseline.

## Notes

[2026-11-13T05:55:32Z · sase-1sl.2] sase-core-revision.txt ratcheted from 3416e4e24c84 to core HEAD bab5978195d9. RUNNER_SLOT_SCAN_OPTIONS already uses capacity_only=True and only_workflow_dirs=(ace-run,), so no Python option adoption was needed. Rebuilt the local dev wheel from sase-core bab59781 via just install-venv. Re-measured the real archive using a hard-linked copy to preserve the live shared cache: 190 retained records; cold scan wall 2.817s / CPU 2.513s; warm scan wall 0.9998s / CPU 0.998s, versus the 22.9s baseline. Warm narrowly meets <1s; cold is 8.1x faster, short of the >=10x target. The live ~/.sase/runner_slots.scan.json stayed 1,062,956 bytes with identical mtime over 12s while host runners were present; this observed a quiet interval, not a forced token bump. PROPOSED FOLLOW-UP: Investigate the real-archive cold capacity-scan result (2.82s, 8.1x vs the 22.9s baseline) and warm scan at the 1s threshold before claiming the stated scan budgets.

[2026-11-13T06:20:32Z · sase-1sl.2] Pinned sase-core revision to bab5978195d9 and confirmed no Python option change was needed. On a hard-linked copy of the real archive: 190 records, cold 2.817s (8.1x vs 22.9s baseline), warm 0.9998s. Live runner scan cache remained unchanged over a quiet 12s observation. just check passed (ToolRun 6aba5705a062f0f46840126c04573aea, exit 0). Follow-up proposal records the shortfall against the >=10x cold target.

## Dependencies

- **Depends on:** [sase-1sl.1](sase-1sl.1.md) ✓ · ⧖ 2026-11-12
- **Blocks:** [sase-1sl.4](sase-1sl.4.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sl.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sl.2/README.md) | [sase-1sl.2](sase-1sl.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9285c4f`](https://github.com/sase-org/sase/commit/9285c4f55eec790693c7bcae9dc88e87a847a21f) | chore(rust): ratchet capacity scan core revision | [sase-1sl.2](sase-1sl.2.md) | 2026-11-13 01:23:18 EST |

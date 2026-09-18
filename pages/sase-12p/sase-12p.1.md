# Bead: sase-12p.1 — Admit BY\_STATUS grouping to the incremental Agents display path

[Bead Pages](../README.md) / [sase-12p](README.md) / sase-12p.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mq.md) · **Assignee:** `sase-12p.1` · **Size:** medium
**Created:** 2026-09-18 06:26:39 EDT · **Closed:** 2026-09-18 07:44:53 EDT
**Plan:** [202609/by\_status\_panels\_and\_stale\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202609/by_status_panels_and_stale_tui.md)

## Description

by-status-incremental: determine the BY_STATUS panel-safety invariants, allow the incremental display diff and row remove paths when the rendered widget tree and status-bucket membership are stable, retain a full rebuild (under a distinct fallback reason) for genuine bucket, hierarchy, or anchor changes, and cover both directions with focused and perf tests.

## Notes

[2026-09-18T11:44:53Z · sase-12p.1] Implemented BY_STATUS incremental Agents display admission and row-remove safety: stable same-bucket updates patch without panel rebuilds, bucket/subgroup/anchor changes fall back with status_membership_change, and unsupported_grouping remains for unsupported modes. Verified focused pytest suite, just fmt, and just check (scoped lane escalated to full fast suite and passed).

## Dependencies

- **Blocks:** [sase-12p.3](sase-12p.3.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12p.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12p.1/README.md) | [sase-12p.1](sase-12p.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1fa7e5f`](https://github.com/sase-org/sase/commit/1fa7e5fc3ac6abed3ac62de65d038c631da167e8) | feat(tui): admit by-status incremental agent refresh | [sase-12p.1](sase-12p.1.md) | 2026-09-18 07:46:39 EDT |

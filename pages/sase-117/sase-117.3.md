# Bead: sase-117.3 — Settlement notification targeting

[Bead Pages](../README.md) / [sase-117](README.md) / sase-117.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0l7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0l7.md) · **Assignee:** `sase-117.3` · **Size:** medium
**Created:** 2026-09-15 09:49:40 EDT · **Closed:** 2026-09-15 11:56:00 EDT
**Plan:** [202609/ace\_family\_status\_convergence.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_family_status_convergence.md)

## Description

settlement-notify-targeting: carry the settled shell's identity in monitor-settlement and epic-launch notification action_data and resolve those notifications to an exact family-chain artifact-dir delta so the status flip lands on the notification's own tick.

## Notes

[2026-09-15T15:56:00Z · sase-117.3] Implemented settlement notification action_data identity and exact family-chain refresh targeting. Verified just check (scoped escalated to full suite), focused notification/epic-launch suites, and convergence targeting repro with downstream merge/apply dependency marked xfail.

## Dependencies

- **Depends on:** [sase-117.1](sase-117.1.md) ✓ · ⧖ 2026-09-15
- **Blocks:** [sase-117.4](sase-117.4.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-117.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-117.3/README.md) | [sase-117.3](sase-117.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4e98613`](https://github.com/sase-org/sase/commit/4e98613a1fbbde4e14a9d28ef738b74786c7454e) | fix(ace): target settlement notification refreshes | [sase-117.3](sase-117.3.md) | 2026-09-15 11:57:57 EDT |

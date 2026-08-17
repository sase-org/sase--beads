# Bead: sase-on.4 — bead\_stale\_cleanup chop

[Bead Pages](../README.md) / [sase-on](README.md) / sase-on.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04x](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04x.md) · **Assignee:** `sase-on.4` · **Size:** medium
**Created:** 2026-08-17 11:47:55 EDT · **Closed:** 2026-08-17 13:47:03 EDT
**Plan:** [202608/task\_bead\_gate\_thresholds.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_gate_thresholds.md)

## Description

chop: extract the shared enabled-project inventory, add the hourly bead_stale_cleanup chop with its own lane state and reconciliation, register it in the housekeeping lumberjack and the console-script table, and drop the epic symbol whitelist entries the earlier phases needed.

## Notes

[2026-08-17T17:47:03Z · sase-on.4] Extracted shared enabled-project inventory to _bead_gate_projects.py (chop-labeled warnings, no re-export from the old module), added the hourly bead_stale_cleanup chop with its own lock/state and fingerprint reconciliation (roster + three thresholds, not stale_as_of), registered it in housekeeping (timeout 2m) and [project.scripts], and dropped the four sase-on --epic-symbol entries. Verified: just check green including an escalated full suite; sase bead epic-symbols sase-on.4 reports no leftovers; chop tests cover below/at-threshold, non-stale exclusion, 50-bead cap + omitted log, unchanged roster, stale_as_of excluded from fingerprint, changed-roster generation bump, below-bar cancel+clear, failed-project no-cancel, inventory failure, dry_run, and two-project oldest-first order.

[2026-08-17T17:48:09Z · sase-on.4] Extracted shared enabled-project inventory; added hourly bead_stale_cleanup chop with lock/state fingerprint reconciliation (roster + three thresholds, not stale_as_of); registered in housekeeping (timeout 2m) and [project.scripts]; dropped four sase-on --epic-symbol entries. Verified: just check green including escalated full suite; sase bead epic-symbols sase-on.4 reports no leftovers; chop tests cover below/at-threshold, non-stale exclusion, 50-bead cap + omitted log, unchanged roster, stale_as_of excluded from fingerprint, changed-roster generation bump, below-bar cancel+clear, failed-project no-cancel, inventory failure, dry_run, and two-project oldest-first order.

## Dependencies

- **Depends on:** [sase-on.1](sase-on.1.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-on.3](sase-on.3.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-on.5](sase-on.5.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-on.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-on.4/README.md) | [sase-on.4](sase-on.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9f5147b`](https://github.com/sase-org/sase/commit/9f5147be365219e79fd4a3a85128c939e2cc5e00) | feat(axe): add hourly bead\_stale\_cleanup chop | [sase-on.4](sase-on.4.md) | 2026-08-17 13:48:55 EDT |

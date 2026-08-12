# Bead: sase-jz.3 — Roll the new ci\_watch out to the live host and verify

[Bead Pages](../README.md) / [sase-jz](README.md) / sase-jz.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yi](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yi/README.md) · **Assignee:** `sase-jz.3` · **Size:** small
**Created:** 2026-08-12 10:39:07 EDT · **Closed:** 2026-08-12 11:47:40 EDT
**Plan:** [202608/retire\_audit\_chops\_and\_gate\_ci\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_audit_chops_and_gate_ci_fixes.md)

## Description

rollout: bump the package version, push bugyi-chops, drop the now-inert `wait_runners: 0` from the `ci_watch` lane, reinstall the plugin from git, and verify with a dry run plus a live tick that the gate path files exactly one gate and no duplicates.

## Notes

[2026-08-12T15:47:03Z · sase-jz.land] Phase-3 agent completed the rollout but exited while waiting on a Monitor, leaving this bead open with no notes. Verified by the land agent from the live host: bugyi-chops 0.5.0 released (4d20317), master pushed, no v0.5.0 tag (latest tag is still v0.3.1, PyPI publish left to the user); chezmoi 731c0e46 dropped the inert 'wait_runners: 0' from the ci_watch lane and rewrote both descriptions for the gate flow; the plugin is installed from git and axe is healthy. Live evidence: the 11:27:00 tick reported fix_gated=1 proposals=0 and filed exactly one LaunchApproval gate (launch-4d63090a, still pending, prompt carries '#gh:sase-org/sase %i:ci_fix.sase.@ %w(runners=0)' plus the #pr/#actstat evidence body), the 11:31:58 tick reported fix_gated=0 gate_pending_suppressed=1 proposals=0 with no second gate, ci_watch_fixes.json is version 2 with that single gate row, and no ci_fix.* agent was ever started without approval.

[2026-08-12T15:47:40Z · sase-jz.land] Rollout verified live; see the preceding note. Land agent also finished the two plan steps phase 3 and phase 1 left undone: removed the orphaned ~/.sase/axe/lumberjacks/code_quality/ state directory (2.1M, lumberjack already unconfigured and its PID dead), and fixed the dry-run hole the gate path shipped with (bugyi-chops 3676814, released 0.5.1 and rolled out).

## Dependencies

- **Depends on:** [sase-jz.2](sase-jz.2.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jz.3/README.md) | [sase-jz.3](sase-jz.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@731c0e4`](https://github.com/bbugyi200/dotfiles/commit/731c0e46384b74709a63a7777bf047a9855e09ca) | chore(sase): drop inert wait\_runners from ci\_watch, describe the gate flow (sase-jz.3) | [sase-jz.3](sase-jz.3.md) | 2026-08-12 11:24:45 EDT |

# Bead: sase-1tz.1.1.3 — Check that starter-inherited repo lists stay inside the monitor's workspace

[Bead Pages](../README.md) / [sase-1tz.1.1](sase-1tz.1.1.md) / sase-1tz.1.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) · **Assignee:** `sase-1tz.1.1.3` · **Size:** small
**Created:** 2026-11-19 07:28:41 EST · **Closed:** 2026-11-19 07:58:34 EST
**Plan:** [202611/outage\_disk\_attribution\_and\_held\_workspaces.md](https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md)

## Description

starter_scope: verify whether closed sase-1rg.3 keeps starter-inherited repo lists from probing another workspace. Fix the gap with a regression test if it does not.

## Notes

[2026-11-19T12:55:42Z · sase-1tz.1.1.3] starter_scope finding: sase-1rg.3 already covers starter-inherited repo lists. collect_monitor_repo_observations scopes foreign starter repos via _scope_foreign_starter_repos (keeps only paths inside the monitor checkout), evidence_artifacts_dir falls back to the monitor dir for foreign starters so _baseline_by_path merges nothing foreign, and carried_repositories contribute only repo_ids (custody flags), never probe paths. Verified end-to-end: live dirty foreign starter repos (baseline + opened marker + carried_repositories under another sase_<N> checkout) release clean with no retention record. Added regression test test_live_foreign_starter_linked_repo_does_not_retain in tests/monitor/test_monitor_retention_lifecycle_baselines.py (9/9 file green; fails when scoping is disabled, proving it guards the fix). No prod-code change needed.

[2026-11-19T12:58:34Z · sase-1tz.1.1.3] No gap: sase-1rg.3 already keeps starter-inherited repo lists inside the monitor workspace. Verified: live dirty foreign starter repos (baseline + opened marker + carried_repositories under another sase_N checkout) release clean with no retention record; new regression test test_live_foreign_starter_linked_repo_does_not_retain green (9/9 file), red when scoping disabled; full sase tool run check green (run dfa13d6a, exit 0). Findings noted on sase-1tz.1.1.3 and sase-1rg.3.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.1.3.md) | [sase-1tz.1.1.3](sase-1tz.1.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`63fc5cc`](https://github.com/sase-org/sase/commit/63fc5ccc4c6fed1adcb09eadc508587338dd508e) | test(monitor): live foreign starter repos do not retain | [sase-1tz.1.1.3](sase-1tz.1.1.3.md) | 2026-11-19 08:02:36 EST |

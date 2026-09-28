# Bead: sase-1bc.10 — Launch-from-view inheritance and launch UX

[Bead Pages](../README.md) / [sase-1bc](README.md) / sase-1bc.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0t4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0t4.md) · **Assignee:** `sase-1bc.10` · **Size:** medium
**Created:** 2026-09-27 10:57:14 EDT · **Closed:** 2026-09-28 15:43:07 EDT
**Plan:** [202609/agents\_dynamic\_tabs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_dynamic_tabs.md)

## Description

launch-view-ux: add the prompt-bar tab chip and remote-tab hint, the gb Launch Tab picker, %tab insertion on submit from a named tab, landing toasts with arrival marks, and the LaunchApproval tab field.

## Notes

[2026-09-28T18:51:59Z · sase-1bc.10] PROPOSED FOLLOW-UP: PNG goldens for the prompt-bar tab chip and gb Launch Tab picker (unit/widget coverage landed; visual goldens still open)

[2026-09-28T19:42:30Z · sase-1bc.10--3] PROPOSED FOLLOW-UP: just check has 4 pre-existing test failures reproducing identically on clean base tree (stashed): test_agent_session_terminology (cli_tab.py agent_family), test_config_schema (tool_runs run_tool/stop_run), test_proc_producer_inventory (stale _launch_catalog_tool entry), test_parser_command_help (agents sorted subcommands); none touch bead-10 files

[2026-09-28T19:42:41Z · sase-1bc.10--3] PROPOSED FOLLOW-UP: symvision gate red on stale --epic-symbol entries for closed bead sase-1bt (RowIdentity, ToolRunGlanceSnapshot, ToolRunLogTail, ToolRunStateStyle) in Justfile:393-398; Justfile unmodified by this bead, owner should remove entries and clean up symbols

[2026-09-28T19:42:53Z · sase-1bc.10--3] PROPOSED FOLLOW-UP: full-suite just check showed 3 timing-sensitive UI failures (launch_context_bar full_cluster, deck_block_spread bracket_top, top_bar busy_cluster) that pass in isolation with bead-10 changes; treat as flaky under load

[2026-09-28T19:43:07Z · sase-1bc.10--3] launch-view-ux done: prompt-bar tab chip + remote hint, gb Launch Tab picker, %tab on submit, landing toasts with arrival marks, LaunchApproval tab field. Verified: 95/95 own tests pass; ruff clean; mypy clean on changed files; sase bead epic-symbols clean (no entries). Full just check: only pre-existing failures, all reproduce on stashed clean tree (4 tests + stale sase-1bt symvision entries, recorded as follow-ups); 3 UI timing failures pass in isolation.

## Dependencies

- **Blocks:** [sase-1bc.12](sase-1bc.12.md) ◐ · ⧖ 2026-09-27
- **Depends on:** [sase-1bc.5](sase-1bc.5.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bc.9](sase-1bc.9.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.10.md) | [sase-1bc.10](sase-1bc.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`995e057`](https://github.com/sase-org/sase/commit/995e057116b84e6e149a161524ca5cfd870f9743) | feat(agents-tabs): launch-from-view inheritance and launch UX | [sase-1bc.10](sase-1bc.10.md) | 2026-09-28 15:44:55 EDT |

# Bead: sase-1nn.8.4.1 — Repair the Python 3.12 CLI and Archive help goldens

[Bead Pages](../README.md) / [sase-1nn.8.4](sase-1nn.8.4.md) / sase-1nn.8.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nn.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.land.md) · **Assignee:** `sase-1nn.8.4.1` · **Size:** medium
**Created:** 2026-10-24 02:46:44 EDT · **Closed:** 2026-10-24 03:30:52 EDT
**Plan:** [202610/v0\_18\_1\_final\_goldens.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_final_goldens.md)

## Description

goldens: integrate the stats and stranded-work changes by repairing their two deterministic golden failures, then verify and land the repair.

## Notes

[2026-10-24T07:15:37Z · sase-1nn.8.4.1] PROPOSED FOLLOW-UP: TUI import budget 3534 vs 3527 cap — identical on clean master 102c6ee847; existing owner sase-1ic. ToolRun a4410b391804673ef10e4cac3164a3fe failed only tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget (57264 passed). Isolated clean-tree pytest reproduced 3534<3527. Local venv count; does not fail release CI. No extra +1.

[2026-10-24T07:16:05Z · sase-1nn.8.4.1] PROGRESS: repaired both goldens on master 102c6ee847. CLI: SASE_UPDATE_PROJECT_RENDER_GOLDENS=1 on isolated py3.12.13 venv /tmp/sase-1nn-841-py312 with sase-core-rs==0.42.3; removed exactly one By repo row and one repos[] jq example in tests/stats/golden/cli/project_help.txt. tests/main/test_parser_stats.py 8 passed on 3.12 and 8 passed on checkout 3.14; py313 golden unchanged. PNG: TZ=UTC just fix-tui-screenshots -- tests/ace/tui/visual/test_ace_png_snapshots_agents_archive_states.py::test_archive_help_png_snapshot applied run f90cd8f3cf654970883cdbd9ba8ae108; changed_pixels=52757/1520532 (3.469641%) matching Full CI job 120783473777. Archive (read-only) title visible, footer restore, 3-row shift from stranded Help legend rows, not a loading frame, unstable=0. Dual-zone --check clean (UTC 16ac39c2ea7f448eb3457a97f6d6cf10 and America/New_York fbabdb110d0e40d7b24ebf95dc47dccc): unchanged=1. just fix clean. epic-symbols empty. Next: full TZ=UTC just fix-tui-screenshots --check then close.

[2026-10-24T07:30:39Z · sase-1nn.8.4.1--1] PROPOSED FOLLOW-UP: TZ=UTC full visual --check run d4a901c6a13640fe92f7c76160b1caf9 (ToolRun 6c6c6de53bcc53f90d06269cd485fd53) was check/clean (created=0 updated=0 unchanged=1122 stale=0); two nodes passed only on recapture after a nearly full-frame first-attempt mismatch: test_agent_session_gate_turns_narrow_png_snapshot (agents_session_panel_turns_gate_90x40.png) and test_renamed_generic_agent_session_root_png_snapshot (agents_renamed_generic_session_root_120x40.png). Plan forbids blindly regenerating the latter. Related settle-path owner for the renamed-session node is sase-1ln. Goldens unchanged; does not keep this phase open.

[2026-10-24T07:30:52Z · sase-1nn.8.4.1--1] Verified both golden repairs on master 102c6ee847. CLI: SASE_UPDATE_PROJECT_RENDER_GOLDENS=1 on isolated Python 3.12.13 venv /tmp/sase-1nn-841-py312 with sase-core-rs==0.42.3 removed exactly one duplicate By repo row and one duplicate repos[] jq example in tests/stats/golden/cli/project_help.txt; tests/main/test_parser_stats.py 8 passed on 3.12 and 8 passed on checkout 3.14; py313 golden unchanged. Resolves sase-1nt for the lander. PNG: TZ=UTC targeted update run f90cd8f3cf654970883cdbd9ba8ae108; changed_pixels=52757/1520532 (3.469641%) matching Full CI job 120783473777; Archive (read-only) title visible, footer restore, 3-row Help legend shift, not a loading frame, unstable=0. Dual-zone check-only clean (UTC 16ac39c2ea7f448eb3457a97f6d6cf10 and America/New_York fbabdb110d0e40d7b24ebf95dc47dccc, unchanged=1). Resolves the archive-help DISCOVERED ISSUE on sase-1no for the lander. Full TZ=UTC just fix-tui-screenshots --check ToolRun 6c6c6de53bcc53f90d06269cd485fd53 exit 0: run d4a901c6a13640fe92f7c76160b1caf9 check/clean, 1388 passed / 1 skipped, created=0 updated=0 unchanged=1122 stale=0; agents_archive_help_120x40.png byte_equal; two recapture-only unstables recorded as PROPOSED FOLLOW-UP (not regenerated). just fix clean. epic-symbols empty. sase tool run check a4410b391804673ef10e4cac3164a3fe: lint green; 1 failed / 57264 passed — tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget 3534 vs 3527, identical on clean master 102c6ee847, existing owner sase-1ic, already recorded as PROPOSED FOLLOW-UP (no extra +1); does not fail release CI and does not keep this phase open.

## Dependencies

- **Blocks:** [sase-1nn.8.4.2](sase-1nn.8.4.2.md) ◐ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.4.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.1.md) | [sase-1nn.8.4.1](sase-1nn.8.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dc2cc11`](https://github.com/sase-org/sase/commit/dc2cc11324f6cd3696603ec56e2458f113936ab1) | test(stats): repair Python 3.12 project help and Archive help goldens | [sase-1nn.8.4.1](sase-1nn.8.4.1.md) | 2026-10-24 03:32:15 EDT |

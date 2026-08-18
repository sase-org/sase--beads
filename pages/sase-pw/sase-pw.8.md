# Bead: sase-pw.8 — sase project current

[Bead Pages](../README.md) / [sase-pw](README.md) / sase-pw.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.062.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.062.f1.md) · **Assignee:** `sase-pw.8` · **Size:** small
**Created:** 2026-08-18 11:30:35 EDT · **Closed:** 2026-08-18 15:51:14 EDT
**Plan:** [202608/current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/current_project.md)

## Description

cli: add the `sase project current` subcommand with colored and `--json` output so the resolved current project is inspectable outside the TUI.

## Notes

[2026-08-18T19:33:09Z · sase-pw.8--1] PROPOSED FOLLOW-UP: just check-full is red on current master because tests/feature_flags/test_integrity.py::test_kind_mismatch_when_default_disagrees_with_kind raises TypeError: demo_flag() got an unexpected keyword argument default after the flag-kind collapse. Not caused by this CLI phase; sase-ps land already recorded it on sase-pv.

[2026-08-18T19:50:33Z · sase-pw.8--2] PROPOSED FOLLOW-UP: tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes failed once in the 422-file serial middle-gear run (scroll_y 0.0 != max_scroll_y 190). Known closed flake sase-jb (baselined); this CLI phase does not touch the Logs pane. Do not file a new bead.

[2026-08-18T19:50:49Z · sase-pw.8--2] PROPOSED FOLLOW-UP: tests/ace/tui/test_plugins_browser_pane_comprehensive_update_confirmation.py::test_comprehensive_confirmation_stays_open_when_submit_collides failed once in the same run (expect_modal PluginActionConfirmModal timed out; last value ConfigCenterModal). Already tracked as ready task sase-oe. This phase does not touch the plugins browser. Do not file a new bead.

[2026-08-18T19:51:14Z · sase-pw.8--2] Shipped sase project current (colored +name/key/origin/MRU-ref and -j/--json; empty MRU exits 0 with how-to-set). Docs, skill source, completion snapshot, and tests are in this workspace. Justfile --epic-symbol cleanup consumed CurrentProject, project_accent, project_accent_map, resolve_current_project; kept sase-pw.4(peek_current_project_change_token). sase bead epic-symbols sase-pw.8: no leftovers. just check: all lint gates passed; test lane escalated on the Justfile rule and timed out after 45m on an exhausted suite-gate pool. Middle-gear 422-file serial selection: 4811 passed, 1 skipped; 2 failures are known flakes (sase-jb logs scroll; ready sase-oe plugin confirm modal), not this CLI. Focused handler/parser/help/skill tests: 71 passed. Live smoke: sase project current and --json both resolve on this host.

[2026-08-18T19:52:11Z · sase-pw.8--2] Shipped sase project current (colored human output + --json), docs/cli.md, docs/configuration.md, sase_project skill, completion snapshot, and Justfile --epic-symbol cleanup consuming CurrentProject, project_accent, project_accent_map, resolve_current_project (kept sase-pw.4 peek_current_project_change_token). Verified: epic-symbols clean; just check lint gates passed (test lane escalated on Justfile rule and timed out on exhausted suite-gate); 422-file serial middle-gear selection 4811 passed / 1 skipped; focused handler/parser/help/skill tests 71 passed. Two middle-gear TUI failures are known flakes (sase-jb, sase-oe), not this CLI.

## Dependencies

- **Depends on:** [sase-pw.1](sase-pw.1.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pw.2](sase-pw.2.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.9](sase-pw.9.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pw.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-pw.8.md) | [sase-pw.8](sase-pw.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a6e374d`](https://github.com/sase-org/sase/commit/a6e374d001efceae220525746865e3f6ac709c2f) | feat(cli): add sase project current | [sase-pw.8](sase-pw.8.md) | 2026-08-18 15:54:58 EDT |

# Bead: sase-cz.5 — PNG snapshot coverage and documentation sweep

[Bead Pages](../README.md) / [sase-cz](README.md) / sase-cz.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qw](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qw/README.md) · **Assignee:** `sase-cz.5` · **Size:** small
**Created:** 2026-08-01 11:04:09 UTC · **Closed:** 2026-08-01 12:46:34 UTC
**Plan:** [202608/bead\_notification\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_notification_panel.md)

## Description

visuals: add PNG snapshot goldens for the Beads tab, the filer meta line, and the task triage action panel, then reconcile the notification and bead documentation with the shipped behavior.

## Notes

[2026-08-01T12:30:37Z · sase-cz.5] PROPOSED FOLLOW-UP: Refresh Config Center config PNG golden — just test-visual fails in tests/ace/tui/visual/test_ace_png_snapshots_config_center_config.py::test_config_center_config_tab_png_snapshot because the actual detail pane now shows axe.chop_script_dirs provenance while the committed golden still shows section-level axe detail.

[2026-08-01T12:45:16Z · sase-cz.5] PROPOSED FOLLOW-UP: Update SDD write-file tests for committed-plan metadata — tests/test_sdd_file_writes.py::test_write_sdd_files_supports_flat_sidecar_plans_root and ::test_write_sdd_files_rebases_seeded_parent_section now fail in isolation because committed-plan validation requires title and goal frontmatter.

[2026-08-01T12:45:40Z · sase-cz.5] PROPOSED FOLLOW-UP: Investigate full-suite-only pytest flakes — just check failed in tests/test_bead/test_cli_work_from_plan_concurrency.py::test_concurrent_plan_file_launches_serialize_through_terminal_push and retry_e2e visual snapshots, but those selectors passed when rerun with SASE_PYTEST_WORKERS=1.

[2026-08-01T12:46:34Z · sase-cz.5] Added Beads-tab, Filed-by meta-line, and Task Triage gate PNG goldens; updated notification tab docs. Verified targeted visual file passed with snapshot update and then twice without update; just test-visual full and just check were run, with unrelated failures recorded as proposed follow-ups.

## Dependencies

- **Depends on:** [sase-cz.2](sase-cz.2.md) ✓
- **Depends on:** [sase-cz.3](sase-cz.3.md) ✓
- **Depends on:** [sase-cz.4](sase-cz.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-cz.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-cz.5/README.md) | [sase-cz.5](sase-cz.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`6a4bb9d`](https://github.com/sase-org/sase/commit/6a4bb9d5bbe242603e6c5cdf6b53cdd3aab0e1d5) | test: add bead notification PNG snapshots | [sase-cz.5](sase-cz.5.md) | 2026-08-01 12:49:04 |

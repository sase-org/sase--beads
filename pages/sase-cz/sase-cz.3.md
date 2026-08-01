# Bead: sase-cz.3 — Panel tabs and filer line in the notification modal

[Bead Pages](../README.md) / [sase-cz](README.md) / sase-cz.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qw](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qw/README.md) · **Assignee:** `sase-cz.3` · **Size:** medium
**Created:** 2026-08-01 11:03:57 UTC · **Closed:** 2026-08-01 12:11:20 UTC
**Plan:** [202608/bead\_notification\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_notification_panel.md)

## Description

inbox: resolve notification modal tabs from the declared panel ahead of the synthetic HITL and Errors tabs, order and label panel tabs, and render the filing agent on the detail pane's meta line.

## Notes

[2026-08-01T11:37:37Z · sase-cz.3] PROPOSED FOLLOW-UP: Deploy regenerated sase_gate provider skill copies after the epic lands — just check validation reports five chezmoi copies lagging the phase-1 source template by six lines; the epic design explicitly forbids running sase skill init from a phase workspace.

[2026-08-01T12:01:34Z · sase-cz.3] PROPOSED FOLLOW-UP: Update SDD writer test fixtures for the August 2026 strict plan schema — tests/test_sdd_file_writes.py::test_write_sdd_files_supports_flat_sidecar_plans_root and ::test_write_sdd_files_rebases_seeded_parent_section deterministically fail in isolation because generated tale frontmatter lacks required title and goal fields.

[2026-08-01T12:02:01Z · sase-cz.3] PROPOSED FOLLOW-UP: Fix slow-tool fold visual footer-state timeout — test_agents_slow_tool_calls_fold_levels_png_snapshots times out waiting for the loaded tools footer both in the full suite and in isolation, despite rendering the slow-tool rows.

[2026-08-01T12:02:20Z · sase-cz.3] PROPOSED FOLLOW-UP: Update SDD writer test fixtures for the August 2026 strict plan schema — tests/test_sdd_file_writes.py::test_write_sdd_files_supports_flat_sidecar_plans_root and ::test_write_sdd_files_rebases_seeded_parent_section deterministically fail in isolation because generated tale frontmatter lacks required title and goal fields.

[2026-08-01T12:02:54Z · sase-cz.3] PROPOSED FOLLOW-UP: Identify and sandbox the test creating /var/tmp/sase-*/opencode — the full suite leak guard reported one unmanaged opencode entry after 25,048 tests.

[2026-08-01T12:03:23Z · sase-cz.3] PROPOSED FOLLOW-UP: Fix slow-tool fold visual footer-state timeout — test_agents_slow_tool_calls_fold_levels_png_snapshots times out waiting for the loaded tools footer both in the full suite and in isolation, despite rendering the slow-tool rows.

[2026-08-01T12:03:51Z · sase-cz.3] PROPOSED FOLLOW-UP: Identify and sandbox the test creating /var/tmp/sase-*/opencode — the full suite leak guard reported one unmanaged opencode entry after 25,048 tests.

## Dependencies

- **Depends on:** [sase-cz.1](sase-cz.1.md) ✓
- **Blocks:** [sase-cz.5](sase-cz.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-cz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-cz.3/README.md) | [sase-cz.3](sase-cz.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`661699f`](https://github.com/sase-org/sase/commit/661699f387a830d107f02a45558e121bdfff494c) | feat(tui): route notifications through declared panels | [sase-cz.3](sase-cz.3.md) | 2026-08-01 12:07:23 |

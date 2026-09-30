# Bead: sase-1d5.7 — TUI audience chips, add-note toggle, and queued uploads

[Bead Pages](../README.md) / [sase-1d5](README.md) / sase-1d5.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tz](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tz.md) · **Assignee:** `sase-1d5.7` · **Size:** medium
**Created:** 2026-09-30 01:57:18 EDT · **Closed:** 2026-09-30 14:34:28 EDT
**Plan:** [202609/public\_bead\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/public_bead_attachments.md)

## Description

tui: show 🌐/🔒 on beads-pane chips. In the add-note modal, run the audience decision off the event loop and add a toggle that narrows freely and widens only with confirmation. Queue TUI-authored attachments into the upload outbox instead of stranding them locally.

## Notes

[2026-09-30T17:59:28Z · sase-1d5.7] Recording phase verification evidence TUI phase done: beads-detail chips pass descriptor visibility to attachment_descriptor (public shows 🌐, else 🔒; no store stats); add-note modal gains an auto→private→public toggle on configurable beads_toggle_note_audience (Ctrl+T, hidden with flag off), runs authoring plus the audience decision in the existing worker thread, confirms public widening via dialog while non-widenable refusals re-open inline; note writes queue through shared pre_write_upload/post_write_queue so the sync worker drains them. Tests: 22 new/updated in test_bead_note_modal, test_beads_detail_body_audience, test_bead_note_upload_queue pass; keymap/catalog/schema/snooze suites (1078) pass; ruff+mypy clean; symvision shows only two pre-existing unrelated items; beads PNG goldens pass with no drift. -r

[2026-09-30T18:33:33Z · sase-1d5.7--1] PROPOSED FOLLOW-UP: just check NEW failure tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed (extra site src/sase/bead/attachments/lifecycle.py:quarantine_local_object) reproduces identically on clean base via git stash (28s isolated run, exit 1); already tracked by task bead sase-1de item 1 — do not fix in this TUI phase

[2026-09-30T18:34:28Z · sase-1d5.7--1] TUI phase verified: 22 phase tests pass (test_bead_note_modal, test_beads_detail_body_audience, test_bead_note_upload_queue); just check NEW failure test_artifact_directory_operation_sites_are_reviewed (extra site lifecycle.py:quarantine_local_object) reproduces identically on clean base via git stash, tracked by sase-1de item 1, recorded as PROPOSED FOLLOW-UP; remaining 14 KNOWN + 1 FLAKY per triage; symvision 2 KNOWN only; epic-symbols empty

## Dependencies

- **Depends on:** [sase-1d5.6](sase-1d5.6.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d5.8](sase-1d5.8.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d5.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d5.7.md) | [sase-1d5.7](sase-1d5.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`909f61f`](https://github.com/sase-org/sase/commit/909f61ffecff7a600b60e8746cc28553e41d6e49) | feat(tui): audience chips, add-note toggle, and queued uploads (sase-1d5.7) | [sase-1d5.7](sase-1d5.7.md) | 2026-09-30 14:36:18 EDT |

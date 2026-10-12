# Bead: sase-1jm.8 — Retire Artifacts ▸ Agent and make the Archive unconditional

[Bead Pages](../README.md) / [sase-1jm](README.md) / sase-1jm.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.45.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.45.linker.w0.md) · **Assignee:** `sase-1jm.8` · **Size:** medium
**Created:** 2026-10-10 06:41:22 EDT · **Closed:** 2026-10-12 13:50:15 EDT
**Plan:** [202610/agents\_archive\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view.md)

## Description

retire-pane: delete the agents_archive_view beta flag's Off branches. Hide the Artifacts Agent sub-tab behind a new sunset flag, renumbering Stitch to 1, with a legacy mapping, a one-time toast, and the explicit-command redirect. Migrate pane saved queries, then update docs, help, goldens, and (if accepted) the glossary.

## Notes

[2026-10-12T17:07:42Z · sase-1jm.8] PROPOSED FOLLOW-UP: Add glossary:agent-archive strand defining the Archive view, in:archive scope, and Restore to inbox (epic decision glossary_archive_term=no skipped it)

[2026-10-12T17:07:48Z · sase-1jm.8] PROPOSED FOLLOW-UP: Update glossary:nav-section, glossary:nav-item, glossary:agent-data-deck, glossary:agent-relation-jump-target for the Archive list, Inbox pulse, shelf, and Record deck (epic decision glossary_strand_updates=no skipped them)

[2026-10-12T17:07:52Z · sase-1jm.8] PROPOSED FOLLOW-UP: symvision NEW finding build_create_plan_request in src/sase/ace/tui/modals/new_project_create.py reproduces identically on the clean base tree (verified via stash); triage as pre-existing

[2026-10-12T17:21:01Z · sase-1jm.8] PROPOSED FOLLOW-UP: test_app_import_budget cap 3513 vs actual 3517 reproduces identically on the clean base tree (verified via stash); needs cap bump or deferral attribution

[2026-10-12T17:31:36Z · sase-1jm.8] PROPOSED FOLLOW-UP: test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data asserts Project: sase but renders tmp; reproduces identically on the clean base tree (verified via stash)

[2026-10-12T17:31:42Z · sase-1jm.8] PROPOSED FOLLOW-UP: TestMetaPatchPriority::test_project_shown_when_no_patch asserts my_project but renders fake; reproduces identically on the clean base tree (verified via stash)

[2026-10-12T17:46:38Z · sase-1jm.8] PROPOSED FOLLOW-UP: Capture PNG goldens for the retired Artifacts strip (Stitch on digit 1, no Agent tab) and the one-time pane-retirement toast; existing Artifacts goldens still mount via _fast_artifacts_subtabs (Agent present) so none drifted. Needs a visual test with production resolve_artifacts_subtabs plus targeted just fix-tui-screenshots run.

[2026-10-12T17:50:03Z · sase-1jm.8] PROPOSED FOLLOW-UP: tests/ace/tui/widgets/test_agent_display_workflow_async.py::test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data fails identically on clean base tree (verified via git stash) and standalone; passes in full-suite ordering — order-dependent test isolation issue, not retire-pane fallout

[2026-10-12T17:50:15Z · sase-1jm.8] Retire-pane complete and verified: agents_archive_view Off-branches deleted (Archive open/toggle/pulse/shelf/arrival/link-follow/jump/Files-a unconditional), flag removed from registry+schema and flag bead sase-1ju closed, Artifacts Agent pane hidden behind sunset flag artifacts_agent_pane_retired (bead sase-1kb) with Stitch renumbered to 1, agents->agents-live pane-query migration, one-time toast, explicit-command redirect; docs ace/cli/query_language updated. Tests: new tests/test_agents_pane_retirement.py 9/9 pass; 248-test targeted sweep 247 pass with the single failure (workflow_async snapshot test) proven base-reproducing via stash; ruff+format clean; epic-symbols clean; remaining full-gate reds recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-1jm.4](sase-1jm.4.md) ✓ · ⧖ 2026-10-10
- **Depends on:** [sase-1jm.5](sase-1jm.5.md) ✓ · ⧖ 2026-10-10
- **Depends on:** [sase-1jm.6](sase-1jm.6.md) ✓ · ⧖ 2026-10-10
- **Depends on:** [sase-1jm.7](sase-1jm.7.md) ✓ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.8/README.md) | [sase-1jm.8](sase-1jm.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`101c853`](https://github.com/sase-org/sase/commit/101c8539399669c266d76c01f44ed1e56b24a814) | feat(ace): retire Artifacts Agent pane and make Agent Archive unconditional | [sase-1jm.8](sase-1jm.8.md) | 2026-10-12 14:08:42 EDT |

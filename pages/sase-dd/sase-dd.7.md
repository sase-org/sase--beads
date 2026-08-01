# Bead: sase-dd.7 — Help, docs, onboarding, and visual snapshots

[Bead Pages](../README.md) / [sase-dd](README.md) / sase-dd.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.r7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.r7/README.md) · **Assignee:** `sase-dd.7` · **Size:** medium
**Created:** 2026-08-01 13:54:08 UTC · **Closed:** 2026-08-01 18:15:47 UTC
**Plan:** [202608/artifacts\_beads\_and\_files\_subtabs.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_beads_and_files_subtabs.md)

## Description

polish: document the new layout in the help modal and the ace guide, refresh onboarding and empty-state copy, complete the copy-mode palette for the new group, and re-record the affected PNG goldens.

## Notes

[2026-08-01T17:47:33Z · sase-dd.7] PROPOSED FOLLOW-UP: Stabilize the Artifacts j/k p95 benchmark — two verification runs exceeded 16 ms in different action groups (commits.up10 at 20.15 ms, then plans.next at 29.76 ms) despite low medians and no changes to those render paths; isolate scheduler noise or use a more robust outlier policy.

[2026-08-01T17:48:50Z · sase-dd.7] PROPOSED FOLLOW-UP: Clear current Symvision unused-public-symbol findings — just check stops on seven symbols in untouched agents-sync, bead, unread-state, and prompt-artifact modules, preventing later checks from running.

[2026-08-01T17:49:34Z · sase-dd.7] PROPOSED FOLLOW-UP: Repair the existing uppercase_active_subtabs plan link — sase validate reports a missing prompt reverse-link and discontiguous/nested plan header bullets in untouched 202607 artifacts.

[2026-08-01T17:52:54Z · sase-dd.7] PROPOSED FOLLOW-UP: Repair test_admin_center_selection_resume collection — it imports _patch_store_loader from test_tasks_pane, but that helper no longer exists; both files are untouched by this phase.

[2026-08-01T17:58:26Z · sase-dd.7] PROPOSED FOLLOW-UP: Update the _FakeApp in test_agent_display_defer_detail — three leader-footer tests fail because the untouched fake lacks the now-required _has_bulk_read_undo_available method.

[2026-08-01T18:02:30Z · sase-dd.7] PROPOSED FOLLOW-UP: Resolve remaining unrelated full-suite failures — agents_sync/prompt_archive imports the ACE layer, show_style_closed_phase.ansi has Rich escape-code drift, and the concurrent bead mutation test intermittently times out on its 5s lock budget.

[2026-08-01T18:15:47Z · sase-dd.7] Implemented Beads/Files help, documentation, onboarding, empty-state copy, Copy-as support, and deterministic PNG coverage. Verified 80 focused behavioral tests; canonical visual suite 405 passed, 1 skipped; mypy passed across 2670 source files; actual sase ace --profile startup exited successfully; committed-plan validation passed; and git diff --check passed. just check was attempted but remains blocked by documented unrelated Symvision, plan-validation, benchmark, and baseline-test issues recorded as PROPOSED FOLLOW-UP notes.

[2026-08-01T18:16:48Z · sase-dd.7] Verified 80 focused behavioral tests, 405 passed/1 skipped visual tests, mypy across 2,670 files, ACE profile startup, committed-plan validation, and git diff --check; unrelated baseline failures recorded as proposed follow-ups.

[2026-08-01T18:17:07Z · sase-dd.7] Verified 80 focused behavioral tests, 405 passed/1 skipped visual tests, mypy across 2,670 files, ACE profile startup, committed-plan validation, and git diff --check; unrelated baseline failures recorded as proposed follow-ups.

## Dependencies

- **Depends on:** [sase-dd.6](sase-dd.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dd.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dd.7/README.md) | [sase-dd.7](sase-dd.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`80d44e3`](https://github.com/sase-org/sase/commit/80d44e38414c1ce4258535271208c6c6be38ad9b) | feat(ace): polish beads and nested files views | [sase-dd.7](sase-dd.7.md) | 2026-08-01 18:18:45 |

# Bead: sase-16e.2 — Self-healing checkout preparation for numbered workspaces

[Bead Pages](../README.md) / [sase-16e](README.md) / sase-16e.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pc.md) · **Assignee:** `sase-16e.2` · **Size:** medium
**Created:** 2026-09-22 12:13:30 EDT · **Closed:** 2026-09-22 15:56:45 EDT
**Plan:** [202609/self\_healing\_workspace\_prep.md](https://github.com/sase-org/sase--plans/blob/main/202609/self_healing_workspace_prep.md)

## Description

checkout-heal: give prepare_workspace an opt-in self-heal ladder for numbered workspaces that rescues state, aborts in-progress git operations, survives stash failures, replaces a conflicting sync rebase with rescue plus hard reset to the default branch, and verifies a clean postcondition.

## Notes

[2026-09-22T19:40:26Z · sase-16e.2] PROPOSED FOLLOW-UP: Repair pre-existing just-check symvision failure on agent_env_refusal_reason (src/sase/service/platform.py) — introduced by landed sase-16g.6 commit 2ce4998e9, used only in-file plus tests plus __all__, fails just _lint-symvision on a tree without this phase work; triaged per sase_new_task with no duplicate task found (nearest is sase-150, different symbols/files)

[2026-09-22T19:49:18Z · sase-16e.2] PROPOSED FOLLOW-UP: Two pre-existing test-lane failures reproduce on pristine HEAD without this phase work — (1) tests/test_timezone_display_guard.py flags a new datetime.now() site at src/sase/ace/tui/actions/agents/_agent_enter_targets.py:278, no duplicate task found; (2) test_preview_modal_resize_recomputes_geometry fails identically here, corroborating READY task sase-16f (same stale-100x30-screen defect, already triaged there)

[2026-09-22T19:56:45Z · sase-16e.2] checkout-heal implemented and verified: self_heal ladder in prepare_workspace (rescue-first, abort all in-progress ops incl. revert/am/bisect/sequencer via one shared helper also used by reset_replay, stash-failure reset/clean fallback, force-checkout plus -B recreate, split fetch with distinct fetch step, conflict rescue plus hard reset, verify postcondition) with reclone_eligible classification; 8 new provider ops on GitCommon; self_heal wired from launch/linked/retry callers. Verified: 15 new real-git tests in tests/test_axe_runner_workspace_self_heal.py pass; 109 pass across all 10 affected suites; ruff/mypy/fmt/keep-sorted and all other lint gates pass. Remaining red (pre-existing on pristine HEAD, recorded as PROPOSED FOLLOW-UP notes): symvision agent_env_refusal_reason, timezone datetime.now site, modal-resize test (sase-16f). Two lane failures caused by this work were fixed in-tree: clean-failure precedence and artifact-audit review entries.

## Dependencies

- **Depends on:** [sase-16e.1](sase-16e.1.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16e.3](sase-16e.3.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16e.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16e.2/README.md) | [sase-16e.2](sase-16e.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`496bd7f`](https://github.com/sase-org/sase/commit/496bd7fbda22b867e246bf10d1f378815fb416cd) | feat(workspace): self-healing checkout preparation for numbered workspaces | [sase-16e.2](sase-16e.2.md) | 2026-09-22 16:00:21 EDT |

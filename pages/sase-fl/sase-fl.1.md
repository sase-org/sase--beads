# Bead: sase-fl.1 — Host-owned launches own their own outcome

[Bead Pages](../README.md) / [sase-fl](README.md) / sase-fl.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tl/README.md) · **Assignee:** `sase-fl.1` · **Size:** medium
**Created:** 2026-08-05 18:31:50 EDT · **Closed:** 2026-08-05 18:50:03 EDT
**Plan:** [202608/epic\_launch\_false\_failure.md](https://github.com/sase-org/sase--plans/blob/main/202608/epic_launch_false_failure.md)

## Description

attribution: stop converting a planner-side SDD store failure into `epic_launch_failed` when the approval response assigned launch ownership to the host, degrade to `epic_approved` with a recorded publication error, and carry that degradation into the completion notification instead of a bogus resume command.

## Notes

[2026-08-05T22:49:09Z · sase-fl.1] PROPOSED FOLLOW-UP: `just lint` symvision fails at HEAD independent of this phase — `progress_fingerprint` in src/sase/llm_provider/commit_finalizer_git.py is reported as an unused public symbol; make it private or delete it.

[2026-08-05T22:49:20Z · sase-fl.1] PROPOSED FOLLOW-UP: tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads.py::test_artifacts_beads_populated_png_snapshot fails at HEAD with a clean tree (details pane renders a scrollbar and wraps the Created "5d ago" line, ~3% material pixel diff) — the snapshot appears time-dependent and needs a pinned clock or refreshed golden.

[2026-08-05T22:49:34Z · sase-fl.1] PROPOSED FOLLOW-UP: the second epic store-failure branch in handle_accepted_plan is unreachable — its try body is entirely `not is_epic`-gated, so an epic can never set store_unusable_error there, which also makes the "prompt archive entry could not be committed" warning dead; either wire epic prompt-archive commits through it or delete the branch.

[2026-08-05T22:50:03Z · sase-fl.1] handle_accepted_plan now splits both epic store-failure branches on _epic_launch_is_host_owned(plan_result) (action=='epic' and epic_launch_owner=='host'). Host-owned: records sdd_publication_error, logs 'the host-owned epic launch continues independently', does NOT call _notify_epic_launch_failure, and falls through to 'epic_approved' (verified every block between the branches and the epic return is not-is_epic-gated, so sdd_store/sdd_plan_path are never dereferenced; store_unusable_error is cleared so the second branch cannot re-fire). Unowned (epic_launch_owner=None): unchanged byte-for-byte — epic_launch_error metadata, _notify_epic_launch_failure with the same args, 'epic_launch_failed'. send_completion_notification appends a degraded note when agent_meta.json carries sdd_publication_error, so it rides the same payload defer_epic_completion hands to the launch (one notification saying both 'epic launched' and 'the planner's archive entry is missing'). Tests: replaced test_unusable_epic_store_stops_before_launcher_with_home_resume with host-owned (epic_approved, no failure notify, sdd_publication_error recorded, no epic_launch_error, write_sdd_spec not called) and unowned (epic_launch_failed + notify args + epic_launch_error) cases; added two finalizer tests covering the degraded note in the deferred payload and its absence otherwise. No assertion weakened. just install + targeted tests (35 passed); just check clean except two failures reproduced at HEAD on a clean tree (symvision progress_fingerprint, artifacts_beads PNG snapshot) — both filed as PROPOSED FOLLOW-UP notes, along with the now-dead second store-failure branch.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fl.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fl.1/README.md) | [sase-fl.1](sase-fl.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`75a1ffc`](https://github.com/sase-org/sase/commit/75a1ffc10692d24c8016ee6574ad901197d1752a) | fix(axe): keep host-owned epic launches alive after an SDD store failure | [sase-fl.1](sase-fl.1.md) | 2026-08-05 18:51:04 EDT |

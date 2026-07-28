# Bead: sase-9v.1 — Serialize the launch-claim mutation under the store write lock

[Bead Pages](../README.md) / [sase-9v](README.md) / sase-9v.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9v.1` · **Size:** small
**Created:** 2026-07-26 15:32:06 UTC
**Plan:** [sase/repos/plans/202607/bead\_review\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/bead_review_hardening.md)

## Description

launch_claim_lock: hold one bead_store_write_lock span across the runner launch-claim mutation and its SDD commit in claim_bead_for_agent_launch, matching the sase-9r.1 contract already enforced on the wait-claim and release paths.

## Notes

Implemented: claim_bead_for_agent_launch now wraps the launch-claim mutation and its SDD commit in one bead_store_write_lock span (in-tree branch holds the lock across the mutation too); publish_bead_claim stays outside the span, matching claims.py. commit_sdd_store_files/commit_sdd_files gained an already_locked flag that hands the store write lock off instead of reacquiring it; commit_sdd_store_files applies the handoff only to the target repo this context actually owns (new sase.sdd._git_contention.store_write_lock_is_held predicate), so a split plans/research store still locks its sibling repo normally. Regression test: tests/test_bead/test_claims.py::test_launch_claim_holds_store_lock_from_materialization_through_commit (verified failing before the fix).

Follow-up NOT done here (cascades, per the plan): commit_epic_graph_checkpoint in src/sase/bead/cli_work_from_plan.py. Its epic-creation mutations happen inside create_and_launch_epic_from_plan, and the checkpoint commit runs much later via the before_agent_launch callback (_checkpoint_and_publish_graph). Closing that span would hold the store write lock across plan-file commits, interactive confirmation prompts, agent launch, and network publication, so it needs its own phase rather than an inline fix.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9v.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9v.1/README.md) | [sase-9v.1](sase-9v.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`26c26fe`](https://github.com/sase-org/sase/commit/26c26fec23542b62be756aad42c559a868e12f73) | fix(beads): serialize the launch-claim mutation under the store write lock (sase-9v.1) | [sase-9v.1](sase-9v.1.md) | 2026-07-26 16:04:52 |

# Bead: sase-1pj.5.1.2 — Split monitor preparation from process launch

[Bead Pages](../README.md) / [sase-1pj.5.1](sase-1pj.5.1.md) / sase-1pj.5.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.md) · **Assignee:** `sase-1pj.5.1.2` · **Size:** medium
**Created:** 2026-10-29 14:48:37 EDT
**Plan:** [202610/monitor\_staging.md](https://github.com/sase-org/sase--plans/blob/main/202610/monitor_staging.md)

## Description

start-transaction: persist a reconstructible staged member, reserve ordinary ToolRuns, launch from persisted inputs after finalization, and clean up unstarted resources on failure or discard. Preserve the existing public start path until activation. Integrate staged member reads, lane exclusion, and ToolRun owner observations.

## Notes

[2026-10-30T07:39:54Z · sase-1pj.5.1.2--8] PROPOSED FOLLOW-UP: tests inherit the launching agent env in monitored just check — SASE_MODEL_OVERRIDE (and agent identity vars) leak into pytest, so a sonnet-launched monitor fails 7 unrelated tests (test_workflow_executor TestShouldHitl x2, test_init_skills_deploy x3, test_sync_checkpoint, test_commit_workflow_publication_outcomes); they pass with SASE_* cleared. Scrub SASE_MODEL_OVERRIDE/SASE_AGENT* in the test-lane env or the autouse conftest.

## Dependencies

- **Depends on:** [sase-1pj.5.1.1](sase-1pj.5.1.1.md) ✓ · ⧖ 2026-10-29
- **Blocks:** [sase-1pj.5.1.3](sase-1pj.5.1.3.md) ◐ · ⧖ 2026-10-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.5.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.1.2.md) | [sase-1pj.5.1.2](sase-1pj.5.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8f982c8`](https://github.com/sase-org/sase/commit/8f982c8ae9a37723b88f7c8c4d95940700b75369) | feat(monitor): split monitor preparation from process launch | [sase-1pj.5.1.2](sase-1pj.5.1.2.md) | 2026-10-30 04:18:23 EDT |

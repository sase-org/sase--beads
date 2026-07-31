# Bead: sase-bv.4 — Render the creator and its agent link in bead detail output

[Bead Pages](../README.md) / [sase-bv](README.md) / sase-bv.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bv.4` · **Size:** medium
**Created:** 2026-07-31 13:12:43 UTC · **Closed:** 2026-07-31 13:35:25 UTC
**Plan:** [202607/bead\_created\_by\_attribution.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_created_by_attribution.md)

## Description

show: add the `CREATED BY` block to the shared bead detail renderer, resolve the hosted agents sidecar URL for `sase bead show`, add `created_by_url` to the detail JSON envelope, and refresh the affected golden fixtures and docs.

## Notes

[2026-07-31T13:24:14Z · sase-bv.4] PROPOSED FOLLOW-UP: Remove stale Symvision epic-symbol exemptions — just check reports sase-bj.3 is closed for CommitMessagePolicy and CommitSubject, so their exemptions and any now-unused symbols need cleanup.

[2026-07-31T13:25:03Z · sase-bv.4] PROPOSED FOLLOW-UP: Refresh stale generated provider skills — sase validate reports init skills --check would overwrite 10 sase_beads and sase_git_commit provider skill files.

[2026-07-31T13:30:45Z · sase-bv.4] PROPOSED FOLLOW-UP: Repair model-completion provider label casing — full just test expects  but the current registry renders .

[2026-07-31T13:31:06Z · sase-bv.4] PROPOSED FOLLOW-UP: Stabilize suite-gate SIGKILL capacity test — test_scaled_suite_runs_share_capacity_and_release_after_sigkill timed out after its child pytest had reached 100%.

[2026-07-31T13:31:36Z · sase-bv.4] PROPOSED FOLLOW-UP: Clarify model-completion provider label casing — full just test expects Codex (gpt53spark) but the current registry renders codex (gpt53spark).

[2026-07-31T13:32:02Z · sase-bv.4] PROPOSED FOLLOW-UP: Reconcile widespread ACE PNG snapshot drift — full just test reports 53 unrelated visual golden mismatches across agent, config-center, inventory, and models views.

[2026-07-31T13:32:46Z · sase-bv.4] PROPOSED FOLLOW-UP: Reconcile widespread ACE PNG snapshot drift — full just test reports 53 unrelated visual golden mismatches across agent, config-center, inventory, and models views.

[2026-07-31T13:33:24Z · sase-bv.4] PROPOSED FOLLOW-UP: Stabilize suite-gate SIGKILL capacity test — test_scaled_suite_runs_share_capacity_and_release_after_sigkill timed out after its child pytest had reached 100 percent.

[2026-07-31T13:33:54Z · sase-bv.4] PROPOSED FOLLOW-UP: Reconcile widespread ACE PNG snapshot drift — full just test reports 53 unrelated visual golden mismatches across agent, config-center, inventory, and models views.

[2026-07-31T13:35:25Z · sase-bv.4] Verified 69 focused bead show and CLI golden tests pass; Python and Markdown formatting, Ruff, mypy, size checks, and committed-plan validation pass; the live agent URL resolver returned the hosted sase-bv.4 agents-sidecar page. Full check and test baseline failures were unrelated and recorded as proposed follow-ups.

[2026-07-31T13:38:32Z · sase-bv.4] Verified 69 focused bead CLI tests; formatting, Ruff, mypy, size checks, committed-plan validation, and live hosted agent-link resolution. Repository-wide unrelated failures were recorded as PROPOSED FOLLOW-UP notes.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bv.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bv.4/README.md) | [sase-bv.4](sase-bv.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`2c15257`](https://github.com/sase-org/sase/commit/2c152578537e50209de8b6e750d4d179182a5e44) | feat(beads): show creator attribution links | [sase-bv.4](sase-bv.4.md) | 2026-07-31 13:39:42 |

# Bead: sase-dr.4 — Concise sase\_new\_task skill and agent policy

[Bead Pages](../README.md) / [sase-dr](README.md) / sase-dr.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rl/README.md) · **Assignee:** `sase-dr.4` · **Size:** medium
**Created:** 2026-08-01 17:11:08 UTC · **Closed:** 2026-08-01 18:56:48 UTC
**Plan:** [202608/task\_bead\_plus\_one.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_plus_one.md)

## Description

agent-guidance: add the generated task-creation skill, route agent prompts and memories through it, and document duplicate and active-epic decisions.

## Notes

[2026-08-01T18:49:48Z · sase-dr.4] PROPOSED FOLLOW-UP: Repair broken July plan reverse link — `sase validate` reports 202607/uppercase_active_subtabs.md missing a valid prompt reverse-link and containing discontiguous or nested plan header bullets; this predates and is unrelated to sase-dr.4.

[2026-08-01T18:54:42Z · sase-dr.4] PROPOSED FOLLOW-UP: Restore the pre-existing full-suite baseline — independent reruns expose an admin-center test import of removed `_patch_store_loader`, three ACE footer fake-app failures missing `_has_bulk_read_undo_available`, an agents-sync→ACE import-boundary violation in prompt_archive/publish.py, and a bead mutation contention regression; the +1 JSON/style golden drift belongs to this epic’s presentation/integration phases.

[2026-08-01T18:56:48Z · sase-dr.4] Verified /sase_new_task generation for agy, Claude, Codex, OpenCode, and Qwen with sase skill init --diff; memory init is drift-free; 65 focused skill/xprompt/memory/ACE tests and the updated ACE PNG snapshot pass; just check passes every formatting and lint lane before expected undeployed-skill and pre-existing plan-link validation failures. Full suite reached 25,329 passes; remaining unrelated and cross-phase failures are recorded in this bead's PROPOSED FOLLOW-UP notes for land-agent triage.

## Dependencies

- **Depends on:** [sase-dr.2](sase-dr.2.md) ✓
- **Blocks:** [sase-dr.5](sase-dr.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dr.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dr.4/README.md) | [sase-dr.4](sase-dr.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`2ec8613`](https://github.com/sase-org/sase/commit/2ec86131dcb38e9b6213723d08a7898b2165f1b5) | feat(beads): add disciplined task creation skill | [sase-dr.4](sase-dr.4.md) | 2026-08-01 18:58:41 |

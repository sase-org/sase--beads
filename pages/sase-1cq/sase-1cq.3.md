# Bead: sase-1cq.3 — Tell agents that host commits happen after the turn ends

[Bead Pages](../README.md) / [sase-1cq](README.md) / sase-1cq.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u6.md) · **Assignee:** `sase-1cq.3` · **Size:** small
**Created:** 2026-09-29 17:21:22 EDT · **Closed:** 2026-09-29 17:51:06 EDT
**Plan:** [202609/cross\_repo\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/cross_repo_landing.md)

## Description

after_turn_messaging: extend sase final submit output, the sase_final skill, and the bd/land_epic tale guidance so agents never defer a closeout waiting for their own host commit.

## Notes

[2026-09-29T21:50:43Z · sase-1cq.3] PROPOSED FOLLOW-UP: just check lint (patch/stitch terminology) fails identically on the clean base tree (14 defects, all in sase-core fixture crates/sase_core/tests/fixtures/note_attachment/at_bearing_notes.jsonl; verified via git stash); not covered by sase-1cm or sase-1cn

[2026-09-29T21:51:06Z · sase-1cq.3] after_turn_messaging done: sase final submit prints an after-turn commit note for commit payloads (names keep/close); sase_final skill step 5 carries the same rule (skill redeploy deferred until land per generated_skills); bd/land_epic tale says the coder commits only after its turn ends and closeout must not wait on own SHA/push/CI. Verified: 60 focused tests pass (new test_final_submit_after_turn_note keep+close, fallback guard, bead close status, defer handler, skill sources); just check lint gates green except pre-existing patch/stitch terminology audit failure reproduced identically on clean base (recorded as PROPOSED FOLLOW-UP); epic-symbols empty.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cq.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cq.3/README.md) | [sase-1cq.3](sase-1cq.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2fe7c65`](https://github.com/sase-org/sase/commit/2fe7c6500fca50ba8036794d595a0e4c7b1912ff) | feat(final): tell agents host commits happen after the turn ends | [sase-1cq.3](sase-1cq.3.md) | 2026-09-29 17:53:00 EDT |

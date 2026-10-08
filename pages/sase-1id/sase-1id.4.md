# Bead: sase-1id.4 — Epic phase and land workers run under %auto:tale

[Bead Pages](../README.md) / [sase-1id](README.md) / sase-1id.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yg.md) · **Assignee:** `sase-1id.4` · **Size:** medium
**Created:** 2026-10-08 13:39:32 EDT · **Closed:** 2026-10-08 16:32:20 EDT
**Plan:** [202610/auto\_p0\_safety\_tales.md](https://github.com/sase-org/sase--plans/blob/main/202610/auto_p0_safety_tales.md)

## Description

epic_workers: emit %auto:tale instead of bare %auto for every phase and land segment. Seed in-process coder and replan successors from the planner's live auto state (per inherit_mode). Flip the bead-work rendering tests and update docs/beads.md.

## Notes

[2026-10-08T20:32:12Z · sase-1id.4] PROPOSED FOLLOW-UP: symvision flags BeadBoardSnapshot (and BeadStoreFingerprint) in src/sase/core/bead_read_facade.py as unused; reproduces identically on the clean base tree (verified via stash round-trip), so unrelated to this phase.

[2026-10-08T20:32:20Z · sase-1id.4] Emits %auto:tale on every phase and land segment (render_multi_prompt); dry-run shows %auto:tale with no bare %auto. Coder and feedback-replan successors seed from live agent_meta.json via overlay helper, inheriting approve plus auto_approve_argument/action (never 'plan'); toggle-off leaves successor with no auto. Flipped 5 rendering test files to :tale assertions and added tests/test_axe_plan_successor_auto_inherit.py (8 tests: inherit, toggle-off, legacy-plan drop, passthrough, relationship persistence). Verified: 69 focused + 191 related tests pass; sase tool run check lint gates green except one symvision NEW (BeadBoardSnapshot) that reproduces identically on the clean base tree. Noted inherit_mode slice on sase-11g. No memory edits (docs_truth owns macros.md). Epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1id.3](sase-1id.3.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1id.6](sase-1id.6.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1id.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1id.4/README.md) | [sase-1id.4](sase-1id.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e6adb11`](https://github.com/sase-org/sase/commit/e6adb110af9f6be222782977c8840e2d91cf7cdf) | feat(bead): run epic phase and land workers under %auto:tale so nested epics wait for review | [sase-1id.4](sase-1id.4.md) | 2026-10-08 16:33:43 EDT |

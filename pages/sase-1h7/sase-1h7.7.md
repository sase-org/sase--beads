# Bead: sase-1h7.7 — Blocker notifications and the cycle guard

[Bead Pages](../README.md) / [sase-1h7](README.md) / sase-1h7.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3v.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3v.linker.w0.md) · **Assignee:** `sase-1h7.7` · **Size:** medium
**Created:** 2026-10-06 18:17:42 EDT · **Closed:** 2026-10-07 17:22:14 EDT
**Plan:** [202610/wait\_for\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md)

## Description

safety: send one deduplicated inbox notification for a LAUNCHING follow past its grace period, for a BLOCKED follow (with the resume command), and for a followed epic whose land agent failed. Fill the reducer's cycle facts, and document the states in docs/axe.md.

## Notes

[2026-10-07T20:46:28Z · sase-1h7.7] PROPOSED FOLLOW-UP: release-phase kill/dismiss path records launching instead of blocked/target_dismissed_during_launch — tests/test_wait_epic_follow_release.py::test_dismiss_launching_target_blocks_without_memoize fails identically on the clean base tree

[2026-10-07T21:21:14Z · sase-1h7.7--1] PROPOSED FOLLOW-UP: just check init repo --check fails identically on clean base tree (sase/repos/beads/README.md +4/-4 drift); needs sidecar guide refresh outside this phase

[2026-10-07T21:21:42Z · sase-1h7.7--1] PROPOSED FOLLOW-UP: just check symvision flags _runs private imports in v2_snapshot_io.py and overview_card.py (triage KNOWN, witness 01bd3ee8622d1d24e562b0d1aab9cc09); files untouched by this phase, not reproducing on phase tree

[2026-10-07T21:22:14Z · sase-1h7.7--1] safety phase verified: 11 new safety tests pass, 40 sibling release/wait-checks tests pass, symvision clean on phase tree; just check leftovers are pre-existing (init-repo README drift identical on base, symvision _runs triage-KNOWN) and recorded as follow-ups

## Dependencies

- **Blocks:** [sase-1h7.10](sase-1h7.10.md) ◐ · ⧖ 2026-10-06
- **Depends on:** [sase-1h7.5](sase-1h7.5.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h7.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.7.md) | [sase-1h7.7](sase-1h7.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7a3e388`](https://github.com/sase-org/sase/commit/7a3e3882c9c1115622e4512a0c6069518f70c47d) | feat(axe): add chop wait epic-follow safety phase with blocker notifications and cycle guard | [sase-1h7.7](sase-1h7.7.md) | 2026-10-07 17:25:41 EDT |

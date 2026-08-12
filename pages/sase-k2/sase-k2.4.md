# Bead: sase-k2.4 — Bug state drives mirrored bead status

[Bead Pages](../README.md) / [sase-k2](README.md) / sase-k2.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yn/README.md) · **Assignee:** `sase-k2.4` · **Size:** large
**Created:** 2026-08-12 11:30:11 EDT
**Plan:** [202608/external\_mirror\_refinement.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_mirror_refinement.md)

## Description

bug_status: reverse the epic's original note-only decision and close or reopen a mirrored bead when its tracker issue closes or reopens, guarded so an in-progress, claimed, or parented bead only gets the note it gets today.

## Notes

[2026-08-12T17:44:25Z · sase-k2.4] PROPOSED FOLLOW-UP: Remove duplicate checks-lane mirror chops — src/sase/default_config.yml still lists external_issue_mirror and external_pr_mirror in both checks and external_mirror lanes, and docs/axe.md still describes checks with three chops; delete the checks-lane copies after lane regression is addressed.

[2026-08-12T17:44:55Z · sase-k2.4] PROPOSED FOLLOW-UP: Decide creation policy for already-closed upstream issues — the mirror still creates a bead open and seeds the current closed state, so no close transition fires on first sight; this belongs to creation/filter policy rather than bug_status.

## Dependencies

- **Depends on:** [sase-k2.2](sase-k2.2.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k2.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-k2.4.md) | [sase-k2.4](sase-k2.4.md) | 0 |

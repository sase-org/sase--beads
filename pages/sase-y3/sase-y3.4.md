# Bead: sase-y3.4 — Heal stranded deletions and add a doctor guardrail

[Bead Pages](../README.md) / [sase-y3](README.md) / sase-y3.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04n.md) · **Assignee:** `sase-y3.4` · **Size:** small
**Created:** 2026-09-07 15:14:48 EDT · **Closed:** 2026-09-07 20:27:03 EDT
**Plan:** [202609/machine\_link\_mutations\_off\_primary.md](https://github.com/sase-org/sase--plans/blob/main/202609/machine_link_mutations_off_primary.md)

## Description

heal-and-guard: add a doctor check for dirty machine-managed sidecar clones under a primary checkout with a restore-based user-invoked fix, propose the one-time restore of the six stranded research link-index deletions through a gate, and file task beads proposing a decisions-web record plus any unpublished-commit retry gap.

## Notes

[2026-09-08T00:25:36Z · sase-y3.4] PROPOSED FOLLOW-UP: memory task bead — decisions-web record capturing that machine link mutations never target a primary checkout nested sidecar clone, hidden host-owned clones are the machine write lane, and the primary converges via pull-based auto-sync.

[2026-09-08T00:25:59Z · sase-y3.4] PROPOSED FOLLOW-UP: unpublished-commit retry/aging — persist link indexes can commit locally and fail to publish; `_unpublished_sidecar_error` does one push_bead_work_launch then errors, with no aging/retry of leftover unpublished sidecar commits (and sase-y3.3 hidden-clone writes are closed as a bead but not on origin/master).

[2026-09-08T00:26:22Z · sase-y3.4] PROPOSED FOLLOW-UP: pre-existing mypy on master — src/sase/pager/_layout.py:168 calls undefined `_measure_section_heights`, so just check lint (mypy) is red independent of this phase; remaining just check gates (fmt, ruff, flags, pyscripts, test waits, changelog, terminology, symvision, toobig, validate, committed plans, test-scoped 3719 passed) were green.

[2026-09-08T00:27:03Z · sase-y3.4] Added project.primary_sidecar_link_dirt doctor check plus sase doctor -R restore-only fix for stranded canonical link-index deletions in primary-nested sidecar clones (does not commit; durable deletions stay on the machine lane). Verified: 21 focused tests passed; fmt/ruff/symvision/toobig/validate/committed-plans green; just test-scoped 3719 passed (escalated: context-baseline-stale). just check mypy is red on pre-existing src/sase/pager/_layout.py:_measure_section_heights (unrelated). One-time heal of 12 unstaged research links/ deletions is proposed via a restore gate rather than mutating the primary clone from this agent.

[2026-09-08T11:07:02Z · sase-y3.4--1] Restore gate custom-c50e0eec-6e09-4af3-896b-91e230d5d077 restored 12 stranded research links/ indexes on the primary nested clone; git status -- links/ is clean, no unstaged deletions, restored paths exist and match HEAD. Did not mutate the primary clone further. Did not close parent epic sase-y3.

[2026-09-08T11:36:08Z · sase-y3.4--1] PROPOSED FOLLOW-UP: stale --epic-symbol entries for closed bead sase-xe — Justfile still lists sase-xe(FollowStoreMutationOutcome), sase-xe(follow_store_path), sase-xe(is_followed), sase-xe(reconcile_follow_store); just check lint (symvision) is now red for unrelated agents. Not this phase; do not re-key from sase-y3.4.

## Dependencies

- **Depends on:** [sase-y3.3](sase-y3.3.md) ✓ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y3.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-y3.4.md) | [sase-y3.4](sase-y3.4.md) | 0 |

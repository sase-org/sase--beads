# Bead: sase-1vt.4 — Conflict replay for unmergeable zero-spawn graph publication

[Bead Pages](../README.md) / [sase-1vt](README.md) / sase-1vt.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1hj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1hj.md) · **Assignee:** `sase-1vt.4` · **Size:** medium
**Created:** 2026-11-27 15:24:25 EST · **Closed:** 2026-11-27 17:49:32 EST
**Plan:** [202611/resilient\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202611/resilient_epic_launch.md)

## Description

replay: carry the integration status out of the managed sync worker, raise a typed publication-conflict error, and in the plan-launch retry loop discard the launch's own unpublished graph commit under a recovery ref and re-mint, with cause-first error text.

## Notes

[2026-11-27T22:49:32Z · sase-1vt.4] Implemented conflict_replay=yes: integration_status carried through managed sync worker into PushOutcome; EpicGraphPublicationConflictError raised on aborted_unsupported_conflicts publication (other failures stay RuntimeError); checkpoint SHA captured and post-rollback tip recorded for the replay safety check; zero-spawn publication conflicts restore only the plan link (no proj.remove) and raise EpicFromPlanError(publication_conflict=True); creation loop discards the unpublished graph under refs/sase/recovery/<epic> after lock+fetch, launch-base-ancestor, attempt-ownership, and clean-worktree checks, then re-mints (bounded by _EPIC_CREATION_MAX_ATTEMPTS, replays counted in timer.fields); refusals and cause-first integration errors (hint/Rebasing noise stripped, git rebase prefix kept) carry manual recovery plus sase doctor -v. Verified: new typed-error/replay/refusal/message tests pass; full tests/test_bead (2845), tests/sdd_store+tests/sdd (833) pass; ruff check+format, mypy src (6751 files), symvision clean (cause-first helper kept private per gate).

## Dependencies

- **Depends on:** [sase-1vt.3](sase-1vt.3.md) ✓ · ⧖ 2026-11-27
- **Blocks:** [sase-1vt.5](sase-1vt.5.md) ◐ · ⧖ 2026-11-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vt.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vt.4/README.md) | [sase-1vt.4](sase-1vt.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5b184c8`](https://github.com/sase-org/sase/commit/5b184c837cd3f6a3f2aeb476e9696c0ea5969d05) | feat(bead): conflict replay for epic graph publication | [sase-1vt.4](sase-1vt.4.md) | 2026-11-27 17:51:12 EST |

# Bead: sase-11e.2 — Public job scripts and SDK

[Bead Pages](../README.md) / [sase-11e](README.md) / sase-11e.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0l8.r0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0l8.r0.md) · **Assignee:** `sase-11e.2` · **Size:** medium
**Created:** 2026-09-15 15:18:42 EDT · **Closed:** 2026-09-15 18:13:35 EDT
**Plan:** [202609/axe\_routines\_jobs.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_routines_jobs.md)

## Previously Closed

> ↺ Closed 2026-09-15T19:31:42Z · canceled
>
> forced by sase-11e: Decided to go with the name Batch instead of Routine.
>
> Reopened 2026-09-15T19:41:04Z by a status update

## Description

job_authoring: add canonical executable, SDK, context, and environment access for job authors without replacing the existing execution engine.

## Notes

[2026-09-15T19:41:13Z · bryanbugyi34@gmail.com] I changed my mind on this. Routine still works better since it implies recurrence.

[2026-09-15T22:13:35Z · sase-11e.2] Implemented public job console aliases, SDK facade, job/chop env aliasing, context routine fields, discovery dedupe, and coverage; verified targeted pytest suite, just _lint-symvision, and just check (full-suite escalation) pass.

## Dependencies

- **Depends on:** [sase-11e.1](sase-11e.1.md) ✓ · ⧖ 2026-09-15
- **Blocks:** [sase-11e.3](sase-11e.3.md) ✓ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11e.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11e.2/README.md) | [sase-11e.2](sase-11e.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f421051`](https://github.com/sase-org/sase/commit/f421051fdda8318c119b2201225337efd3f3398d) | feat(axe): add public job authoring aliases | [sase-11e.2](sase-11e.2.md) | 2026-09-15 18:15:15 EDT |

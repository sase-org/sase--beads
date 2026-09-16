# Bead: sase-11e.4 — Canonical configuration and AXE presentation

[Bead Pages](../README.md) / [sase-11e](README.md) / sase-11e.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0l8.r0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0l8.r0.md) · **Assignee:** `sase-11e.4` · **Size:** medium
**Created:** 2026-09-15 15:18:44 EDT · **Closed:** 2026-09-15 21:29:51 EDT
**Plan:** [202609/axe\_routines\_jobs.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_routines_jobs.md)

## Previously Closed

> ↺ Closed 2026-09-15T19:31:42Z · canceled
>
> forced by sase-11e: Decided to go with the name Batch instead of Routine.
>
> Reopened 2026-09-15T19:41:04Z by a status update

## Description

config_tui: connect public configuration views and editors, update defaults and schema, and rename visible AXE and automation-tribe text.

## Notes

[2026-09-15T19:41:13Z · bryanbugyi34@gmail.com] I changed my mind on this. Routine still works better since it implies recurrence.

[2026-09-16T01:28:43Z · sase-11e.4] PROPOSED FOLLOW-UP: Restore Rust/Python core wire alignment before relying on full-suite just check - current install reports git_object_sharing and agent_artifact_run_retention wire schema 3 while Python expects 2; this also blocks sase repo open for linked repos and caused 42 full-suite failures after phase 4 changes.

[2026-09-16T01:29:11Z · sase-11e.4] PROPOSED FOLLOW-UP: Move job/chop tribe collision diagnostics into shared core once sase-core can be opened - phase 4 added local @job presentation and compatibility aliasing, but the design-owned Rust collision path needs the stale wire blocker cleared first.

[2026-09-16T01:29:51Z · sase-11e.4] Verified no epic-symbol entries; focused AXE/config/job presentation suite passed (233 tests), and just check passed lint lanes before full-suite escalation failed on unrelated stale Rust/Python wire schema mismatches recorded as follow-ups.

## Dependencies

- **Depends on:** [sase-11e.3](sase-11e.3.md) ✓ · ⧖ 2026-09-15
- **Blocks:** [sase-11e.5](sase-11e.5.md) ✓ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11e.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11e.4/README.md) | [sase-11e.4](sase-11e.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`53ba460`](https://github.com/sase-org/sase/commit/53ba46064937d53c3c3c9902542aadf5fe3831bb) | feat(axe): publish routine and job presentation | [sase-11e.4](sase-11e.4.md) | 2026-09-15 21:31:54 EDT |

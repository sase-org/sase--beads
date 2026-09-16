# Bead: sase-11e.3 — Commands, structured output, and reference presentation

[Bead Pages](../README.md) / [sase-11e](README.md) / sase-11e.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0l8.r0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0l8.r0.md) · **Assignee:** `sase-11e.3` · **Size:** medium
**Created:** 2026-09-15 15:18:43 EDT · **Closed:** 2026-09-15 20:12:08 EDT
**Plan:** [202609/axe\_routines\_jobs.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_routines_jobs.md)

## Previously Closed

> ↺ Closed 2026-09-15T19:31:42Z · canceled
>
> forced by sase-11e: Decided to go with the name Batch instead of Routine.
>
> Reopened 2026-09-15T19:41:04Z by a status update

## Description

cli_contract: expose axe routine and axe job commands, public JSON projections, diagnostics, and job reference spelling while preserving stored identities.

## Notes

[2026-09-15T19:41:13Z · bryanbugyi34@gmail.com] I changed my mind on this. Routine still works better since it implies recurrence.

[2026-09-16T00:12:08Z · sase-11e.3] Implemented public AXE job/routine CLI, JSON diagnostics, and job artifact-ref alias contract; verified linked sase-core just check, refreshed rust binding, focused AXE/artifact tests, and primary just check.

## Dependencies

- **Depends on:** [sase-11e.2](sase-11e.2.md) ✓ · ⧖ 2026-09-15
- **Blocks:** [sase-11e.4](sase-11e.4.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11e.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11e.3/README.md) | [sase-11e.3](sase-11e.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d2d3094`](https://github.com/sase-org/sase/commit/d2d30944dce4c0dc0f10e78d9e568ea758630765) | feat(axe): publish job and routine cli contract | [sase-11e.3](sase-11e.3.md) | 2026-09-15 20:13:59 EDT |
| sase-core | [`sase-core@6be757c`](https://github.com/sase-org/sase-core/commit/6be757c19565003c75d61efdf89cb7764adeec6b) | feat(artifact-ref): add job alias for chop refs | [sase-11e.3](sase-11e.3.md) | 2026-09-15 20:16:09 EDT |

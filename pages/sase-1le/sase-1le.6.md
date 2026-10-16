# Bead: sase-1le.6 — Change-to-docs routing rule for agents and a constrained refresh\_docs chop

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.6` · **Size:** small
**Created:** 2026-10-15 18:11:10 EDT · **Closed:** 2026-10-15 19:35:31 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

routing: add the docs_writing.md reference memory note and constrain the refresh_docs chop prompts to page types, budgets, and the Guide tier's fix-only rule.

## Notes

[2026-10-15T23:35:21Z · sase-1le.6] PROPOSED FOLLOW-UP: test_fix_uses_formatter_venv_without_application_setup fails identically on clean base (KNOWN, witness db73a1a196996a991ac3162fbbebd342); needs a task bead if none tracks it

[2026-10-15T23:35:31Z · sase-1le.6] Added sase/memory/docs_writing.md routing note (in generated reference list after sase memory init); constrained refresh_docs update+polish prompts to contract types/budgets/routing, single-mode, split-over-grow, fix-only Guide steps, no moves, report disagreements; new prompt tests pass (9/9 chop file). sase tool run check: 838 passed, 1 KNOWN pre-existing failure reproduced on clean base.

## Dependencies

- **Blocks:** [sase-1le.20](sase-1le.20.md) ◐ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.5](sase-1le.5.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.6/README.md) | [sase-1le.6](sase-1le.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8947f92`](https://github.com/sase-org/sase/commit/8947f92b3a52e487f226cc32aecc29f3f17a9b3e) | feat(docs): add docs\_writing routing note and constrain refresh\_docs chop (sase-1le.6) | [sase-1le.6](sase-1le.6.md) | 2026-10-15 19:57:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.6][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.6/README.md

<!-- sase:referenced-by:end -->

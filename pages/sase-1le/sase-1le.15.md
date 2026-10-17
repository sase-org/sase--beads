# Bead: sase-1le.15 — Plan and automate guides

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.15

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.15` · **Size:** medium
**Created:** 2026-10-15 18:11:13 EDT · **Closed:** 2026-10-15 23:11:08 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

guides-automate: write the three plan-and-automate guides from sdd.md, beads.md, axe.md, and mentors.md.

## Notes

[2026-10-16T03:10:59Z · sase-1le.15] PROPOSED FOLLOW-UP: just fmt-docs-check fails on pre-existing render_glossary/render_design_decisions drift in docs/reference/glossary.md and docs/reference/design-decisions.md (phase sase-1le.8 pipeline; also recorded in epic note #1 by sase-1le.9); unrelated to this phase, check fails identically on base

[2026-10-16T03:11:08Z · sase-1le.15] Wrote guides/plan-multi-agent-change.md, guides/schedule-recurring-work.md, guides/get-automated-code-review.md; wired guides/index.md hub, mkdocs.yml Plan-and-automate nav, and Do-it links in concepts work-units/automation/landing; repointed 3 stale getting_started.md concept links to start/index.md. Verified: check_docs ok, just docs-check strict build green + URL contract 301/301. just check stops only at pre-existing fmt-docs-check glossary/design-decisions drift (recorded as PROPOSED FOLLOW-UP, sase-1le.8 pipeline).

## Dependencies

- **Depends on:** [sase-1le.12](sase-1le.12.md) ✓ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.13](sase-1le.13.md) ✓ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.20](sase-1le.20.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.15](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.15/README.md) | [sase-1le.15](sase-1le.15.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`da699e0`](https://github.com/sase-org/sase/commit/da699e0236303182503dce685f81036143336300) | docs(guides): add Plan and automate how-to guides | [sase-1le.15](sase-1le.15.md) | 2026-10-15 23:12:46 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.14--1][1] | Check whether earlier phases or the parent already record the clean-base generated-doc formatting failure | 2 |
| read-by | [agent:sase-1le.15][2] | Need the phase scope and design file | 3 |
| read-by | [agent:sase-1le.17][3] | Check existing phase notes for the same generated-doc renderer drift | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.14.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.15/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.17/README.md

<!-- sase:referenced-by:end -->

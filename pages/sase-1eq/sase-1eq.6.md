# Bead: sase-1eq.6 — Documentation, site redirect, memory, and first skill redeploy

[Bead Pages](../README.md) / [sase-1eq](README.md) / sase-1eq.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v4.md) · **Assignee:** `sase-1eq.6` · **Size:** medium
**Created:** 2026-10-02 06:51:28 EDT · **Closed:** 2026-10-03 14:09:43 EDT
**Plan:** [202610/xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/xprompts_to_macros.md)

## Description

docs-memory: redeploy the generated skills and rewrite docs, README, and blog. Move the docs page with a redirect from the old URL. Rename the xprompts memory note and the five glossary strands, then republish memory.

## Notes

[2026-10-03T17:52:38Z · sase-1eq.6] PROPOSED FOLLOW-UP: Regenerate docs/images/macro-resolution-infographic.png labels (still renders retired xprompt paths/commands); files renamed and prompt.md/critique.md rewritten, PNG pixels deferred

[2026-10-03T18:07:12Z · sase-1eq.6] PROPOSED FOLLOW-UP: 26 full-suite failures reproduce identically on clean base (stashed docs-memory tree, 26 failed/2 passed) incl stale macro-vocabulary assertions test_non_skill_in_a_skill_source_is_rejected and test_workflow_wins_over_shadowed_macro; evidence run 86613abea4ddf907d4404e232ede0b47

[2026-10-03T18:09:43Z · sase-1eq.6] docs-memory done: skills redeployed (28 written, chezmoi 8a40f665 applied); docs/xprompt.md moved to docs/macros.md with mkdocs-redirects plus hosting redirect, 1458-spot rewrite, renamed-from section, blog draft renamed and 1 published note; memory note plus 5 strands renamed and republished with reads verified; guard widened (3 new tests); just fmt, docs strict build, memory init --check, 363 focused tests green; full check shows only 2 KNOWN lints and 26 base-repro failures plus 2 flakes (follow-ups noted)

## Dependencies

- **Blocks:** [sase-1eq.11](sase-1eq.11.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1eq.4](sase-1eq.4.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.6/README.md) | [sase-1eq.6](sase-1eq.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fe53ae4`](https://github.com/sase-org/sase/commit/fe53ae4fc46f5e23b3ec44060f2bbbcac2b9bc4c) | feat(docs-memory): rename xprompt concept to macro across docs, memory, and skills | [sase-1eq.6](sase-1eq.6.md) | 2026-10-03 14:18:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.6][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.6/README.md

<!-- sase:referenced-by:end -->

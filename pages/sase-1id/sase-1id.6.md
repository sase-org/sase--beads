# Bead: sase-1id.6 — Docs, memory, and /sase\_questions describe shipped behavior

[Bead Pages](../README.md) / [sase-1id](README.md) / sase-1id.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yg.md) · **Assignee:** `sase-1id.6` · **Size:** medium
**Created:** 2026-10-08 13:39:33 EDT · **Closed:** 2026-10-09 02:34:33 EDT
**Plan:** [202610/auto\_p0\_safety\_tales.md](https://github.com/sase-org/sase--plans/blob/main/202610/auto_p0_safety_tales.md)

## Description

docs_truth: rewrite the %auto passages in docs/macros.md and docs/ace.md to match the landed behavior. Rewrite the macros.md memory %auto row (macros_row). Add the recommended-option-first guidance to the /sase_questions skill source with a test. Close task bead sase-1hh when done.

## Notes

[2026-10-09T06:34:23Z · sase-1id.6--1] PROPOSED FOLLOW-UP: just check _lint-test-waits flags tests/ace/tui/test_plan_decision_ace_stale.py:183,310 inline-pause-wait; file untouched by docs_truth phase (git diff --name-only excludes it) and HEAD contains identical loops, so failure reproduces on clean base tree

[2026-10-09T06:34:33Z · sase-1id.6--1] docs_truth verified: docs/macros.md closed %auto vocabulary (plan/tale/epic/manual/off, paren forms rejected), docs/ace.md A-toggle takes effect at next gate, docs/cli.md and docs/sdd.md auto-approved note tier-scoped, sase/memory/macros.md row rewritten (README tokens ratcheted), sase_questions skill gains Recommended-Option-First section with test_init_skills_sources.py phrase check passing (19 passed); sase-1hh already closed 2026-10-09; epic-symbols clean; just check red only on pre-existing _lint-test-waits in untouched test_plan_decision_ace_stale.py:183,310 (identical on HEAD), recorded as PROPOSED FOLLOW-UP

## Dependencies

- **Depends on:** [sase-1id.1](sase-1id.1.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1id.2](sase-1id.2.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1id.3](sase-1id.3.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1id.4](sase-1id.4.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1id.5](sase-1id.5.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1id.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.6.md) | [sase-1id.6](sase-1id.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c58ae74`](https://github.com/sase-org/sase/commit/c58ae7491ad6ed341dfc91743f989e8623d84eab) | docs(sase-1id.6): align %auto docs with tier-scoped auto-approved truth | [sase-1id.6](sase-1id.6.md) | 2026-10-09 02:37:13 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1id.6--1][1] | check notes and remaining work before repair | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.6.md

<!-- sase:referenced-by:end -->

# Bead: sase-1gt.3 — Remove recurring Master Gate test races

[Bead Pages](../README.md) / [sase-1gt](README.md) / sase-1gt.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ww](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ww.md) · **Assignee:** `sase-1gt.3` · **Size:** medium
**Created:** 2026-10-05 12:16:24 EDT · **Closed:** 2026-10-05 13:14:32 EDT
**Plan:** [202610/fix\_sase\_ci\_failures.md](https://github.com/sase-org/sase--plans/blob/main/202610/fix_sase_ci_failures.md)

## Description

gate-flakes: fix five recurring order and timing races. They are launch-context rebroadcast identity, the AcePage pump-task drain plus onboarding refresh rescheduling, the non-leader kill wait, the shared aggregate-runtime cache, and the panel-shell semicolon press racing the grammar load.

## Notes

[2026-10-05T17:13:47Z · sase-1gt.3--1] PROPOSED FOLLOW-UP: tests/test_macro_terminology.py::test_macro_docs_and_memory_avoid_xprompt_terms fails on clean base (verified via git stash): docs/images/macro-resolution-infographic.prompt.md lists 11 old->new xprompt spelling lines not in _MACRO_DOCS_ALLOWLIST; needs allowlist or prompt-file reword, owned outside gate-flakes scope

[2026-10-05T17:14:12Z · sase-1gt.3--1] PROPOSED FOLLOW-UP: tests/ace/tui/widgets/test_prompt_tab_focus_steal.py (5 failed + 5 teardown errors incl. FrontmatterPanel NoMatches #frontmatter-raw, DuplicateIds launch-context-source, focus isolation leak) fails identically on clean base (verified via git stash); needs a dedicated race/owner triage outside gate-flakes scope

[2026-10-05T17:14:32Z · sase-1gt.3--1] gate-flakes: all 5 races fixed per plan (launch-context rebroadcast identity asserts calls[0] is pre-refresh state; pump-task drain prunes done tasks in a bounded loop + onboarding/launch-target refreshers drop pending follow-up on CancelledError with new drain unit test; non-leader kill waits on runner+same-group child; aggregate wires+result caches both cleared; panel-shell presses wait on grammar readiness with 5s budget). Touched modules green incl. repetition: runtime_tick_caches+ace_testing 48 passed, launch_context_source 23 passed, panel_shell_pilot 10 passed, terminate non-leader 2 passed. Full just check (monitor q0an24jtqha4, 33m) shows only 2 failures, both verified identical on clean base via git stash and recorded as PROPOSED FOLLOW-UP: macro-terminology xprompt allowlist + prompt_tab_focus_steal teardown races. No epic-symbol leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gt.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1gt.3.md) | [sase-1gt.3](sase-1gt.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3569571`](https://github.com/sase-org/sase/commit/3569571a737f2ab31aacc97bdc3c7e1b16b742b4) | fix(gate-flakes): remove five recurring Master Gate test races | [sase-1gt.3](sase-1gt.3.md) | 2026-10-05 13:15:43 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1gt.3--1][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1gt.3.md

<!-- sase:referenced-by:end -->

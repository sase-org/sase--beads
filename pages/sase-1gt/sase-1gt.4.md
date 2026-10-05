# Bead: sase-1gt.4 — Fix scheduled Full CI perf-floors, visual-test, and timing flakes

[Bead Pages](../README.md) / [sase-1gt](README.md) / sase-1gt.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ww](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ww.md) · **Assignee:** `sase-1gt.4` · **Size:** small
**Created:** 2026-10-05 12:16:26 EDT · **Closed:** 2026-10-05 13:27:40 EDT
**Plan:** [202610/fix\_sase\_ci\_failures.md](https://github.com/sase-org/sase--plans/blob/main/202610/fix_sase_ci_failures.md)

## Description

full-ci: stop the hermetic tool-runs smoke from requiring the live-only DoD-17 to pass, pin the output-variables PNG snapshot to paged decks and regenerate its stale golden, and make the startup-clock and proc-query budget assertions immune to runner load.

## Notes

[2026-10-05T17:27:09Z · sase-1gt.4--1] PROPOSED FOLLOW-UP: just check test(scoped) has 5 failed + 5 errors all in tests/ace/tui/widgets/test_prompt_tab_focus_steal.py; reproduces identically on clean base tree (changes stashed, serial file run: same 5 failed + 5 errors). Already tracked by task bead sase-1fy (just +1 corroborated with this repro); new evidence there: serial-only runs now fail too, with wait_for/AcePageGroup-leak signature variance solo.

[2026-10-05T17:27:20Z · sase-1gt.4--1] PROPOSED FOLLOW-UP: just check test(scoped) fails tests/test_macro_terminology.py::test_macro_docs_and_memory_avoid_xprompt_terms; reproduces identically on clean base tree (changes stashed). Cause: docs/images/macro-resolution-infographic.prompt.md contains un-allowlisted xprompt terms (infographic source prompt lines, e.g. inline xprompt, xprompt swarm, sase/xprompts/ paths). No existing task bead names this node (searched avoid_xprompt|macro_docs: none). Likely belongs with legacy_xprompt_syntax retirement (flag bead sase-1fj): either regenerate the infographic PNG + prompt or extend _MACRO_DOCS_ALLOWLIST.

[2026-10-05T17:27:40Z · sase-1gt.4--1] Phase work done and verified. just check run 4378e799592632616eb699362f69373d: all lint gates green (fmt python/markdown/generated-docs, lint, symvision, contract); test(scoped) 52695 passed, 17 skipped; only failures are 3 KNOWN triaged nodes that reproduce identically on the clean base tree (verified via stash: macro_terminology 1 failed, focus_steal 5 failed + 5 errors) and are recorded as PROPOSED FOLLOW-UP notes (focus_steal tracked by sase-1fy, corroborated +1). Targeted passes on this tree: gc_telemetry+proc_query 44 passed; smoke non-slow 4 passed; slow hermetic smoke passed inline (145s); PNG snapshot --check clean with regenerated golden. epic-symbols: zero entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gt.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1gt.4.md) | [sase-1gt.4](sase-1gt.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1c9a2cd`](https://github.com/sase-org/sase/commit/1c9a2cd5df1f90c5d8bf2f8e1ca81d858b2092e3) | fix(ci): stop full-ci perf-floor, visual, and timing flakes | [sase-1gt.4](sase-1gt.4.md) | 2026-10-05 13:29:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1gt.4--1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1gt.4.md

<!-- sase:referenced-by:end -->

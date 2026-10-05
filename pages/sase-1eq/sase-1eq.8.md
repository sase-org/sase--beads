# Bead: sase-1eq.8 — sase-github, sase-research-artifacts, and bugyi-chops cutover

[Bead Pages](../README.md) / [sase-1eq](README.md) / sase-1eq.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v4.md) · **Assignee:** `sase-1eq.8` · **Size:** small
**Created:** 2026-10-02 06:51:31 EDT · **Closed:** 2026-10-03 13:47:22 EDT
**Plan:** [202610/xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/xprompts_to_macros.md)

## Description

plugins: register the sase_macros entry-point group next to the legacy group, keep the packaged xprompts/ directories for now, and use new-first imports in tests. Rename docs and internals in all three plugins.

## Notes

[2026-10-03T17:46:56Z · sase-1eq.8] PROPOSED FOLLOW-UP: bugyi-chops just check has 4 pre-existing failures (test_sase_planning_emits_one_summary_and_promotes_a_surviving_tail, 3x test_sase_bridge_*) asserting lumberjack wait-runner queue prompts; they fail identically on the clean base tree against published sase 0.17.0, unrelated to the macro cutover

[2026-10-03T17:47:22Z · sase-1eq.8] plugins cutover done: sase_macros registered next to sase_xprompts in sase-github + sase-research-artifacts (both groups verified via entry_points, publish smokes assert both), packaged xprompts/ dirs kept, new-first imports in R tests (tests/sase_macro_compat.py, test_macro_loading.py resolves sase.macro.loader_sources, 6 research macros load) + B test (fallback verified vs sase 0.17.0), docs/macros.md renames + stale xprompts.pr_diff claim fixed, internals/docstrings renamed. Checks: G sase tool run check ok (258 passed), R sase tool run check ok (ruff+mypy clean, 94 passed), B just check lint clean + 124 passed with 4 failures proven pre-existing on clean base (recorded as PROPOSED FOLLOW-UP). No epic-symbols remain.

## Dependencies

- **Blocks:** [sase-1eq.10](sase-1eq.10.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1eq.4](sase-1eq.4.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.8/README.md) | [sase-1eq.8](sase-1eq.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.8][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.8/README.md

<!-- sase:referenced-by:end -->

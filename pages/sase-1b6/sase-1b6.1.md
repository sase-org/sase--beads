# Bead: sase-1b6.1 — Core substitution helper and LSP support

[Bead Pages](../README.md) / [sase-1b6](README.md) / sase-1b6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.2a](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2a.md) · **Assignee:** `sase-1b6.1` · **Size:** medium
**Created:** 2026-09-27 08:18:53 EDT · **Closed:** 2026-09-27 08:43:08 EDT
**Plan:** [202609/snippet\_project\_variable.md](https://github.com/sase-org/sase--plans/blob/main/202609/snippet_project_variable.md)

## Description

core-snippet-vars: in sase-core, add the snippet_variables substitution helper, an additive `variables` field on the snippet-session Plan event, and LSP snippet-completion substitution resolved from the document's leading project tag or VCS ref, then the catalog's current project, with tests.

## Notes

[2026-09-27T12:42:39Z · sase-1b6.1] PROPOSED FOLLOW-UP: sase-core gate clippy fails on clean base tree too — 9 pre-existing clippy-1.95.0 lints (nonminimal_bool etc.) in agent_runtime, agent_scan/index/maintenance, finalizer/run_view/decode x2, fleet_owner_facts, provider_usage x2, tool_run/store/receipt, tool_run/store/triage; none in phase-1 files; verified identical via stash + ./scripts/check.sh clippy

[2026-09-27T12:43:08Z · sase-1b6.1] Phase 1 done in sase-core: new snippet_variables module (PROJECT_SNIPPET_VARIABLE + substitute_snippet_variables with unit tests), additive variables field on Plan event with substitution before plan_snippet_expansion (core + binding round-trip tests), LSP active_snippet_project helper (leading tag/VCS ref then current row, no root-basename fallback) applied to snippet candidates with 4 completion tests. Verified: cargo check clean, fmt-check/features pass, full tests for sase_core/sase_xprompt_lsp/sase_core_py green (3641+218+220 etc., 0 failures), just modules lists snippet_variables. sase tool run check blocked only by 9 pre-existing clippy-1.95.0 errors reproducing identically on the clean base tree (recorded as PROPOSED FOLLOW-UP). No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1b6.2](sase-1b6.2.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1b6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1b6.1/README.md) | [sase-1b6.1](sase-1b6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@73f1044`](https://github.com/sase-org/sase-core/commit/73f104486e9827fe7d83295ce5c80bf13d8b6dc3) | feat(snippets): add #{project} substitution helper, Plan variables, and LSP resolution | [sase-1b6.1](sase-1b6.1.md) | 2026-09-27 08:44:39 EDT |

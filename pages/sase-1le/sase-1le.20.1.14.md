# Bead: sase-1le.20.1.14 — Move integration pages and the single-topic reference pages

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.14

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.14` · **Size:** medium
**Created:** 2026-10-16 08:04:38 EDT · **Closed:** 2026-10-16 13:40:53 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

integrations-move: move plugins, editor, completion, mobile_gateway, and remote_dispatch into reference/integrations/ and the six single-topic pages into reference/, then update the cli_rules.md and dispatch.md memory pointers.

## Notes

[2026-10-16T17:40:15Z · sase-1le.20.1.14] PROPOSED FOLLOW-UP: Allowlist the four HEAD xprompt compatibility-anchor lines in docs/_meta/moves.yml, docs/_meta/splits/macros.yml, docs/macros.md, and docs/reference/config/feature-flags.md — test_macro_docs_and_memory_avoid_xprompt_terms fails identically on clean 39f9ca9300; same four lines recorded in sase-1le.20.1.13 note #9 with KNOWN witness dfe062c91ee577b484390ddbf0c7633f.

[2026-10-16T17:40:20Z · sase-1le.20.1.14] PROPOSED FOLLOW-UP: Exclude docs/contribute/perf-runbook.md (hyphen) from test_active_sources_and_docs_use_only_canonical_plan_paths — the test still skips only perf_runbook.md (underscore) and flags the unchanged HEAD file sdd/epics/202604/tui_perf_overhaul_1.md; recorded in sase-1le.20.1.13 notes #8-#9 with KNOWN witness dfe062c91ee577b484390ddbf0c7633f.

[2026-10-16T17:40:53Z · sase-1le.20.1.14] integrations-move complete: split plugins.md and mobile_gateway.md into reference/integrations plus contribute plugin-api and mobile-gateway-api; whole-moved editor, completion, remote-dispatch, query-language, agent-attachments, prompt-history, artifact-references, and artifact-links; updated mkdocs nav, hubs, Related scaffolding, code/test/memory pointers (cli_rules.md, dispatch.md), and docs_move nav rewrite so hyphenated sibling paths are not rewritten. Pinned ## Command Plugins {#command-plugins-1} so MkDocs strict mode resolves the split mapping. Verified just fix; just docs-check (strict build + 2448 URLs); 13 focused docs_move and agent-session terminology tests; epic-symbols none. sase tool run check 7bd3fc063eb0421b4d2e8609eac17845 passed fmt/lint/validation and 4169 tests; two NEW scoped failures match clean HEAD 39f9ca9300 (xprompt allowlist + perf-runbook canonical paths) and are recorded as PROPOSED FOLLOW-UP citing sase-1le.20.1.13.

## Dependencies

- **Depends on:** [sase-1le.20.1.13](sase-1le.20.1.13.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.15](sase-1le.20.1.15.md) ◐ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.20](sase-1le.20.1.20.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.14](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.14/README.md) | [sase-1le.20.1.14](sase-1le.20.1.14.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6a26d90`](https://github.com/sase-org/sase/commit/6a26d909459ec8eb483b04dd90512b38561a9cce) | docs: move integration pages into reference/integrations and contribute | [sase-1le.20.1.14](sase-1le.20.1.14.md) | 2026-10-16 13:42:33 EDT |

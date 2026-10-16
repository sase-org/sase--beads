# Bead: sase-1le.20.1.10 — Move provider and memory pages into reference/providers/ and reference/memory/

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.10` · **Size:** medium
**Created:** 2026-10-16 08:04:37 EDT · **Closed:** 2026-10-16 10:50:16 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Previously Closed

> ↺ Closed 2026-10-16T14:00:03Z · done
>
> (none)
>
> Reopened 2026-10-16T14:30:02Z by a status update

## Description

providers-move: split llms.md (retargeting render_model_docs), agent_providers.md, instruction_bundles.md, memory.md, and memory_history.md into reference/providers/ and reference/memory/, with invocation internals going to contribute/.

## Notes

[2026-10-16T13:37:36Z · sase-1le.20.1.10] providers-move done pending check: llms.md split to reference/providers/ (11 pages) + contribute/llm-invocation.md + upgrading/providers.md; agent_providers.md moved to providers/agent-clis.md; memory.md to memory/memory.md; memory_history.md to memory/history.md; instruction_bundles.md split to memory/instruction-bundles.md + contribute/instruction-bundle-internals.md; render_model_docs retargeted via BLOCK_FILES map; tools/docs_move nav-regex fixed for end-of-line paths; nav/hubs/pointers updated; just fix green (stubs + stale ceilings dropped); sase tool run check run 85ebd61cfff652d011852e01fb66f42a joined to verify monitor

[2026-10-16T13:59:51Z · sase-1le.20.1.10--2] PROPOSED FOLLOW-UP: Nine clean-base extensionless-tool mypy errors (5 in tools/render_keymap_macro_reference, 4 in tools/docs_split) block full just check; files unmodified by this phase so failure reproduces on base — already tracked by sase-1le.20.1.3 and sase-1le.20.1.7 notes

[2026-10-16T14:00:03Z · sase-1le.20.1.10--2] providers-move done: llms.md split to reference/providers/ (11 pages) + contribute/llm-invocation.md + upgrading/providers.md; agent_providers.md to providers/agent-clis.md; memory.md to memory/memory.md; memory_history.md to memory/history.md; instruction_bundles.md split; render_model_docs retargeted; docs_move nav-regex fixed; render_moves now pipes stubs through Prettier so just fix is stable (fmt generated docs + sase-backed + markdown + ruff green, check_docs ok, prettier/render checks green, test_render_webs_prettier + test_docs_moves + test_render_docs pass); full just check blocked only by 9 clean-base mypy errors in unmodified tools/docs_split + tools/render_keymap_macro_reference (recorded as PROPOSED FOLLOW-UP, already tracked by sase-1le.20.1.3/1le.20.1.7); epic-symbols none

[2026-10-16T14:30:03Z · bryanbugyi34@gmail.com] I'm not sure if this work is completed or not but the agent that was attempting to work on it failed.

[2026-10-16T14:48:29Z · sase-1le.20.1.10] PROPOSED FOLLOW-UP: Fix the nine clean-base mypy errors in tools/render_keymap_macro_reference (5) and tools/docs_split (4); sase tool run check 915a487050d68d6c7c4afd47e6e77852 reproduced the same diagnostics in these unchanged files, already tracked by sase-1le.20.1.3 and sase-1le.20.1.7.

[2026-10-16T14:50:16Z · sase-1le.20.1.10] Moved the provider and memory pages into reference/providers/ and reference/memory/, sent invocation and bundle internals to contribute/, moved legacy provider metadata to reference/upgrading/, and retargeted model-table rendering. Verified with just fix, just docs-check (strict build and 1,184 URL checks), 19 focused pytest cases, git diff --check, and epic-symbols (none). sase tool run check reached mypy and stopped on nine unchanged extensionless-tool diagnostics in tools/render_keymap_macro_reference and tools/docs_split; recorded as a PROPOSED FOLLOW-UP citing sase-1le.20.1.3 and sase-1le.20.1.7.

## Dependencies

- **Blocks:** [sase-1le.20.1.11](sase-1le.20.1.11.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.18](sase-1le.20.1.18.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.3](sase-1le.20.1.3.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.10/README.md) | [sase-1le.20.1.10](sase-1le.20.1.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e297cef`](https://github.com/sase-org/sase/commit/e297cefb8ec146cce6cc83e2f56abe43c44572c6) | feat(docs): move provider and memory reference pages | [sase-1le.20.1.10](sase-1le.20.1.10.md) | 2026-10-16 10:51:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.10][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.10/README.md

<!-- sase:referenced-by:end -->

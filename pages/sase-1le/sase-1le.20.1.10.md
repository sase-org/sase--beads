# Bead: sase-1le.20.1.10 — Move provider and memory pages into reference/providers/ and reference/memory/

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.10

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.10` · **Size:** medium
**Created:** 2026-10-16 08:04:37 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

providers-move: split llms.md (retargeting render_model_docs), agent_providers.md, instruction_bundles.md, memory.md, and memory_history.md into reference/providers/ and reference/memory/, with invocation internals going to contribute/.

## Notes

[2026-10-16T13:37:36Z · sase-1le.20.1.10] providers-move done pending check: llms.md split to reference/providers/ (11 pages) + contribute/llm-invocation.md + upgrading/providers.md; agent_providers.md moved to providers/agent-clis.md; memory.md to memory/memory.md; memory_history.md to memory/history.md; instruction_bundles.md split to memory/instruction-bundles.md + contribute/instruction-bundle-internals.md; render_model_docs retargeted via BLOCK_FILES map; tools/docs_move nav-regex fixed for end-of-line paths; nav/hubs/pointers updated; just fix green (stubs + stale ceilings dropped); sase tool run check run 85ebd61cfff652d011852e01fb66f42a joined to verify monitor

## Dependencies

- **Blocks:** [sase-1le.20.1.11](sase-1le.20.1.11.md) ◐ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.18](sase-1le.20.1.18.md) ◐ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.3](sase-1le.20.1.3.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.1.10.md) | [sase-1le.20.1.10](sase-1le.20.1.10.md) | 0 |

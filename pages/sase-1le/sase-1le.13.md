# Bead: sase-1le.13 — Guides hub plus the Set up and Fix problems guides

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.13` · **Size:** medium
**Created:** 2026-10-15 18:11:12 EDT · **Closed:** 2026-10-15 22:55:48 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

guides-setup: create guides/index.md and seven goal-titled guides, folding troubleshooting/* and agent_auto_restart.md into them.

## Notes

[2026-10-16T02:55:35Z · sase-1le.13] PROPOSED FOLLOW-UP: docs build drift pre-exists on base — render_glossary and render_design_decisions report drift from sase/memory sources this phase never touched, failing fmt-docs-check

[2026-10-16T02:55:40Z · sase-1le.13] PROPOSED FOLLOW-UP: strict mkdocs build fails on 3 stale getting_started.md links in concepts/automation.md, memory.md, prompts.md left by the start phase; files untouched by guides-setup

[2026-10-16T02:55:48Z · sase-1le.13] guides-setup done: hub + 7 goal-titled guides (250-345 words each), 3 source pages moved to reference/ with moves.yml redirects, all inbound links retargeted, nav updated. Verified: check_docs ok, prettier clean, strict-build link warnings are only the 3 pre-existing getting_started links (noted as follow-ups), every old URL redirects and every new page exists and is in nav, all documented commands run against master

## Dependencies

- **Depends on:** [sase-1le.11](sase-1le.11.md) ✓ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.14](sase-1le.14.md) ◐ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.15](sase-1le.15.md) ◐ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.17](sase-1le.17.md) ◐ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.19](sase-1le.19.md) ◐ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.9](sase-1le.9.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.13/README.md) | [sase-1le.13](sase-1le.13.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bfa7804`](https://github.com/sase-org/sase/commit/bfa78040ebac10a348ba84bc0b97175bbe3d3ab9) | docs(guides): add setup and fix-problems guides, move recovery pages to reference | [sase-1le.13](sase-1le.13.md) | 2026-10-15 22:57:30 EDT |

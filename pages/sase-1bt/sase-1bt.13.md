# Bead: sase-1bt.13 — User docs for ToolRuns in the TUI

[Bead Pages](../README.md) / [sase-1bt](README.md) / sase-1bt.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tc.md) · **Assignee:** `sase-1bt.13` · **Size:** small
**Created:** 2026-09-27 18:32:53 EDT · **Closed:** 2026-09-28 13:59:10 EDT
**Plan:** [202609/tool\_runs\_tui\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_runs_tui_surfaces.md)

## Description

docs: document the shipped surfaces, vocabulary, keys, and Admin Center tab renumbering in docs/ace.md, docs/tool.md, and docs/configuration.md, and record ready-to-apply glossary text as a PROPOSED FOLLOW-UP note.

## Notes

[2026-09-28T17:51:10Z · sase-1bt.13] PROPOSED FOLLOW-UP: apply ToolRun TUI glossary updates — agent-data-deck strand: change "Tools (the LLM Calls card)" to "Tools (the ⚒ Runs card first, then LLM Calls)"; llm-calls strand: replace "named SASE tools and future ToolRuns are separate control-plane concepts" with "ToolRuns surface on the sibling ⚒ Runs card, which LLM Calls rows link to (verdict suffix + jump) instead of copying"; tool-run strand: append "In the TUI a run surfaces as a live-only ⚒ row chip on its owner node, a header chip plus Tool runs field on the selection, a ⚒ Runs block (waterfall, triage, log tail) on the Tools deck, and project-wide in Admin Center Tools (tab 7); the TUI never reconciles."; optional new verdict-bucket strand: "Bucket is the core-computed ToolRun outcome word (running, pass, new_failures, known_only, undetermined, stopped, killed, lost) rendered as glyph+word+color on every surface; silent is TUI-derived (no sample for 60s), never a core state."

[2026-09-28T17:58:49Z · sase-1bt.13] PROPOSED FOLLOW-UP: sase validate fails on clean base (init memory --check wants sase/memory/sase_artifacts.md +3/-3 and README.md +2/-2 regeneration); blocks sase tool run check for docs-only phases

[2026-09-28T17:59:10Z · sase-1bt.13] Documented shipped ToolRun TUI surfaces in docs/ace.md (new Agents Tab Tool Runs section: vocabulary, row/header chips, Runs card, links, stop/run flows; fixed stale deck-picker FINAL/n and Tools-deck rows; Tools tab stop/run keys), docs/tool.md (In the TUI section), docs/configuration.md (tool_runs keymap scope, %r copy key, tabs 1-8); recorded glossary text + base-tree validate failure as PROPOSED FOLLOW-UP notes. Verified: just fmt clean; sase tool run check fails identically on clean base (init memory --check drift, pre-existing); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1bt.12](sase-1bt.12.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bt.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.13/README.md) | [sase-1bt.13](sase-1bt.13.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7fc18e6`](https://github.com/sase-org/sase/commit/7fc18e6325c4e60789b0421985fe3d5ed98a6c2d) | docs(tui): document ToolRun surfaces, keys, and Admin Center tab | [sase-1bt.13](sase-1bt.13.md) | 2026-09-28 14:00:46 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bt.13][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.13/README.md

<!-- sase:referenced-by:end -->

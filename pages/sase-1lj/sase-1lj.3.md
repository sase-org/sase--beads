# Bead: sase-1lj.3 — Nested tools/, ace/, and tapes/ guides reach every provider

[Bead Pages](../README.md) / [sase-1lj](README.md) / sase-1lj.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10r](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10r.md) · **Assignee:** `sase-1lj.3` · **Size:** medium
**Created:** 2026-10-16 15:15:57 EDT · **Closed:** 2026-10-16 18:59:20 EDT
**Plan:** [202610/e4\_readable\_agents\_md.md](https://github.com/sase-org/sase--plans/blob/main/202610/e4_readable_agents_md.md)

## Description

nested-guides: per decision nested_guides, either fold the three hand-written nested guides into reference notes and delete the six nested files, or keep them with stale lines fixed.

## Notes

[2026-10-16T22:24:57Z · sase-1lj.3] PROPOSED FOLLOW-UP: Instruction-file count is 5 not 2 because sase-1lj.2 closed without retiring root GEMINI.md, QWEN.md, and OPENCODE.md (see sase-1lj.2 notes #6 and #7); nested sets are deleted. `sase memory init` still recreates the three root copies from PROVIDER_SHIM_FILES.

[2026-10-16T22:58:32Z · sase-1lj.3] PROPOSED FOLLOW-UP: tests/test_content_layout.py still expects GEMINI.md/QWEN.md/OPENCODE.md in the project layout while sase-core already returns AGENTS.md+CLAUDE.md — same sase-1lj.2 leftover as notes #6/#7; KNOWN on check abba57d9354f1a41c5244fdf49627092.

[2026-10-16T22:58:41Z · sase-1lj.3] PROPOSED FOLLOW-UP: test_root_help_renders_compact_help expects "Inspect loaded memory, review proposals, and audit reference memory activity." but sase memory help is "Inspect SASE memory context..."; reproduces without this phase's parser_memory.py selector-help edit.

[2026-10-16T22:58:46Z · sase-1lj.3] PROPOSED FOLLOW-UP: test_project_labels_never_derive_from_paths still fails on repair_archived_prompt_path Path(project_file).parent.name — already recorded on sase-1lj.2 note #3; KNOWN on this check.

[2026-10-16T22:59:20Z · sase-1lj.3] Folded nested tools/, ace/, and tapes/ guides into sase/memory/tools.md, ace.md, and demos.md (audited stale help-modal and Vim-syntax paths against current code); merged the obsolete public-API-whitelist fact into symvision.md; deleted the three nested instruction sets (AGENTS.md, CLAUDE.md, and leftover GEMINI/QWEN/OPENCODE copies). sase memory init --check exits 0 once the new notes are staged; sase instructions render lists proj.ref.ace, proj.ref.demos, and proj.ref.tools; epic-symbols had no leftovers. Instruction-file count is 5 (root AGENTS.md+CLAUDE.md plus unreired GEMINI/QWEN/OPENCODE from sase-1lj.2). sase tool run check abba57d9354f1a41c5244fdf49627092 was no_new_failures; remaining KNOWN/pre-existing failures recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-1lj.2](sase-1lj.2.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1lj.5](sase-1lj.5.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lj.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lj.3/README.md) | [sase-1lj.3](sase-1lj.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8fde75d`](https://github.com/sase-org/sase/commit/8fde75d7ae6dedce07d38e342d8d974f2cf4b815) | feat(memory): fold nested tools/ace/tapes guides into reference notes | [sase-1lj.3](sase-1lj.3.md) | 2026-10-16 19:28:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lj.3][1] | Need notes, remaining work, and design file path | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lj.3/README.md

<!-- sase:referenced-by:end -->

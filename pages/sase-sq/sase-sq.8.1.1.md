# Bead: sase-sq.8.1.1 — Remove config glossary and legacy command infrastructure

[Bead Pages](../README.md) / [sase-sq.8.1](sase-sq.8.1.md) / sase-sq.8.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-sq.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.8.md) · **Assignee:** `sase-sq.8.1.1` · **Size:** medium
**Created:** 2026-08-24 23:10:53 EDT · **Closed:** 2026-08-24 23:53:41 EDT
**Plan:** [202608/retire\_config\_glossary.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_config_glossary.md)

## Description

retire-core: remove config-backed glossary, CLI, completion, migration, and generated-note code while preserving the strand matcher and legacy read-history compatibility under memory modules.

## Notes

[2026-08-25T03:53:08Z · sase-sq.8.1.1] PROPOSED FOLLOW-UP: Fix unrelated symvision private-import violations in src/sase/history/chat_fork — just check currently fails in lint (symvision) on _blockquote, _fork_source_*, _format_* and related helpers outside this phase changeset.

[2026-08-25T03:53:41Z · sase-sq.8.1.1] Verified: just install completed; focused glossary/config-retirement suite passed (140 tests); completion snapshot regenerated; sase bead epic-symbols sase-sq.8.1.1 reported no entries. just check reached symvision after fmt/ruff/mypy and failed on unrelated clean files under src/sase/history/chat_fork; recorded a PROPOSED FOLLOW-UP on this bead.

## Dependencies

- **Blocks:** [sase-sq.8.1.2](sase-sq.8.1.2.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sq.8.1.3](sase-sq.8.1.3.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.8.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sq.8.1.1/README.md) | [sase-sq.8.1.1](sase-sq.8.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cebab38`](https://github.com/sase-org/sase/commit/cebab38a1f9b793c59c0671954aab837ab76aee3) | feat(memory): retire config glossary infrastructure | [sase-sq.8.1.1](sase-sq.8.1.1.md) | 2026-08-24 23:55:11 EDT |

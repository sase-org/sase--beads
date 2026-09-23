# Bead: sase-16n.4 — sase-xprompt-lsp project tag support

[Bead Pages](../README.md) / [sase-16n](README.md) / sase-16n.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pl.md) · **Assignee:** `sase-16n.4` · **Size:** medium
**Created:** 2026-09-22 18:48:48 EDT · **Closed:** 2026-09-22 20:14:31 EDT
**Plan:** [202609/project\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags.md)

## Description

lsp: tag completion with in-place edits, semantic tokens with accent modifiers plus a palette capability, hover, diagnostics, quick fixes and a rewrite-to-tag code action, and leading-project detection that understands tags.

## Notes

[2026-09-23T00:13:57Z · sase-16n.4] PROPOSED FOLLOW-UP: v5 catalog wire carries no enabled/disabled state or workspace_dir, so LSP hover/docs show key/aliases/current and provider-less stands in for disabled — extend wire if land wants full D2 fields

[2026-09-23T00:14:31Z · sase-16n.4] LSP tag support landed in sase-core: +label completion with docs/sortText, saseProjectTag tokens + palette capability, hover, D3 diagnostics, quickfix + rewrite-to-tag actions, tag-aware leading project. Verified: 12 new project_tags tests + full sase tool run check green; epic-symbols clean

## Dependencies

- **Depends on:** [sase-16n.1](sase-16n.1.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16n.8](sase-16n.8.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.4/README.md) | [sase-16n.4](sase-16n.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3da8a03`](https://github.com/sase-org/sase-core/commit/3da8a0309ff0b15c44b5869f6af5808479582b8c) | feat(lsp): sase-xprompt-lsp project tag support | [sase-16n.4](sase-16n.4.md) | 2026-09-22 20:15:55 EDT |

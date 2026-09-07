# Bead: sase-xz.2 — Offset-preserving syntax spans and adaptive palette

[Bead Pages](../README.md) / [sase-xz](README.md) / sase-xz.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03g.md) · **Assignee:** `sase-xz.2` · **Size:** medium
**Created:** 2026-09-07 10:51:42 EDT · **Closed:** 2026-09-07 11:40:10 EDT
**Plan:** [202609/pager\_filetype\_syntax.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_filetype_syntax.md)

## Description

syntax_engine: implement bounded Pygments token spans, corrected Markdown frontmatter and fence offsets, source-style preservation, and a restrained theme-adaptive palette without activating a production call site.

## Notes

[2026-09-07T15:40:10Z · sase-xz.2] Implemented inactive pager syntax engine, Markdown offset scanner, adaptive palette, direct Pygments dependency, and focused tests; verified uv run pytest tests/pager/test_syntax.py tests/pager/test_syntax_theme.py, just _lint-symvision, just check, and sase bead epic-symbols sase-xz.2.

## Dependencies

- **Blocks:** [sase-xz.3](sase-xz.3.md) ◐ · ⧖ 2026-09-07
- **Blocks:** [sase-xz.4](sase-xz.4.md) ◐ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xz.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xz.2/README.md) | [sase-xz.2](sase-xz.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0aa7cb9`](https://github.com/sase-org/sase/commit/0aa7cb9e965b504f08a6b3fccef69b84902c03a7) | feat(pager): add inactive syntax span engine | [sase-xz.2](sase-xz.2.md) | 2026-09-07 13:24:59 EDT |

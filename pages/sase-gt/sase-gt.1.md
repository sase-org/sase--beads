# Bead: sase-gt.1 — Collapse every prose-width declaration onto one source of truth

[Bead Pages](../README.md) / [sase-gt](README.md) / sase-gt.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uj](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uj/README.md) · **Assignee:** `sase-gt.1` · **Size:** medium
**Created:** 2026-08-07 08:37:37 EDT · **Closed:** 2026-08-07 08:53:48 EDT
**Plan:** [202608/prettier\_width\_100.md](https://github.com/sase-org/sase--plans/blob/main/202608/prettier_width_100.md)

## Description

unify: introduce sase.markdown_width as the single width authority plus a package.json prettier config block, rewire all five Python declaration sites and both Justfile recipes to derive from them, and add a guard test that fails if any site re-forks the number. No width change and no Markdown reflow in this phase.

## Notes

[2026-08-07T12:53:48Z · sase-gt.1] Added src/sase/markdown_width.py (MARKDOWN_PRINT_WIDTH=120 + prettier_markdown_argv()) as the single width authority and mirrored it in a package.json prettier block; verified prettier --find-config-path resolves to package.json and the tree checks clean with no CLI flags. Rewired all five Python sites (file_references, _init_skills_rendering, init_memory/formatting, memory/notes, markdown_wrap) to derive from it and dropped --prose-wrap/--print-width from both Justfile recipes. Added tests/test_markdown_print_width.py: package.json mirror, argv policy, Justfile-has-no-width regex, a src/ scan for stray prettier prose flags, and an AST scan for width constants bound to bare int literals; proved all three guards fail when I temporarily re-forked package.json width, the Justfile flag, and markdown_wrap's constant, then restored. Rewired the 120-hardcoding tests (test_format_with_prettier, test_init_skills_formatting, init_memory_handler_helpers' prettier_command, test_init_memory_formatting, test_init_memory_managed_agents) to derive from the constant and replaced the markdown_wrap tautology with an assertion that both names resolve to MARKDOWN_PRINT_WIDTH. Verified just check-full passes, git diff --stat -- '*.md' is empty (no width change, no reflow), just fmt-md-check passes, and sase init --check reports no drift.

## Dependencies

- **Blocks:** [sase-gt.2](sase-gt.2.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gt.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gt.1/README.md) | [sase-gt.1](sase-gt.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c37e68f`](https://github.com/sase-org/sase/commit/c37e68f7a5bcf73ceaa90923cb60a12ffd91b7e0) | refactor: collapse every prose-width declaration onto one source of truth | [sase-gt.1](sase-gt.1.md) | 2026-08-07 08:55:19 EDT |

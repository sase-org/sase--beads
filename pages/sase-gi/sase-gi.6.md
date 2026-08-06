# Bead: sase-gi.6 — Ordered-marker highlighting

[Bead Pages](../README.md) / [sase-gi](README.md) / sase-gi.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ub](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ub/README.md) · **Assignee:** `sase-gi.6` · **Size:** small
**Created:** 2026-08-06 15:23:25 EDT · **Closed:** 2026-08-06 16:42:25 EDT
**Plan:** [202608/prompt\_ordered\_lists.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_ordered_lists.md)

## Description

highlight: give ordered markers the same theme-aware accent the leading bullet dash already gets, with unit coverage and a PNG snapshot fixture.

## Notes

[2026-08-06T20:42:25Z · sase-gi.6] Extended _bullet_highlight.py with theme-aware ordered-marker highlighting (bullet.ordered style sharing bullet.dash's Style); added tests/ace/tui/widgets/test_prompt_ordered_highlight.py (17 cases: span boundaries, indented markers, ) delimiters, multi-digit numbers, no false positives on mid-prose digits or tab indents, coexistence with search/yank, UTF-8 byte columns, theme-change re-registration) and PNG snapshot coverage (ORDERED_HIGHLIGHT_SOLO fixture + dark/light goldens, inspected visually). Verified: just lint (ruff, mypy, symvision, keep-sorted, changelog) all pass; unit suite 40/40 passed; just test-visual ordered-highlight snapshots 2/2 passed against goldens; just test-scoped full run 1681/1681 passed.

## Dependencies

- **Depends on:** [sase-gi.1](sase-gi.1.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gi.7](sase-gi.7.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gi.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.6/README.md) | [sase-gi.6](sase-gi.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f7f479a`](https://github.com/sase-org/sase/commit/f7f479a55ba1a6f7bfb5130e6ab8314f831b9b17) | feat(ace-tui): highlight ordered-list markers like bullet dashes | [sase-gi.6](sase-gi.6.md) | 2026-08-06 16:43:17 EDT |

# Bead: sase-1gt.2 — Fix Master Gate's persistent textual-ansi failure and the FrontmatterPanel teardown race

[Bead Pages](../README.md) / [sase-1gt](README.md) / sase-1gt.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ww](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ww.md) · **Assignee:** `sase-1gt.2` · **Size:** small
**Created:** 2026-10-05 12:16:23 EDT · **Closed:** 2026-10-05 12:47:19 EDT
**Plan:** [202610/fix\_sase\_ci\_failures.md](https://github.com/sase-org/sase--plans/blob/main/202610/fix_sase_ci_failures.md)

## Description

gate-deterministic: decouple the terminal-native syntax-palette test from Textual's builtin theme catalog, which renamed textual-ansi in 8.2. Make FrontmatterPanel.on_mount tolerate a Mount dispatched while the panel is being pruned, with a regression test.

## Notes

[2026-10-05T16:46:44Z · sase-1gt.2] PROPOSED FOLLOW-UP: test_macro_docs_and_memory_avoid_xprompt_terms fails identically on clean base tree (verified via git stash) — pre-existing docs-terminology failure unrelated to gate-deterministic

[2026-10-05T16:47:00Z · sase-1gt.2] PROPOSED FOLLOW-UP: test_foreground_run_records_context_usage_and_grant failed once in full check run (peak_tree_rss_kib==0 under load1 40-60) but passes in isolation on both base and patched trees — load-sensitive RSS sampling flake, unrelated to gate-deterministic

[2026-10-05T16:47:19Z · sase-1gt.2] gate-deterministic done: syntax-palette test builds explicit terminal-native Theme (dark+light) and covers all terminal-native BUILTIN_THEMES entries instead of indexing textual-ansi; FrontmatterPanel.on_mount catches NoMatches and returns early with regression test test_on_mount_without_composed_children_does_not_raise (fails pre-fix, passes post-fix). Targeted: 7 passed (syntax theme + new test), full frontmatter file 36 passed. sase tool run check f4802ad1c283bf34bb775a5abf30360b: 52700 passed, 2 failed — macro_terminology fails identically on clean base (pre-existing, noted as follow-up), demand_runs RSS assertion passes in isolation on both trees (load flake, noted). epic-symbols: none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gt.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gt.2/README.md) | [sase-1gt.2](sase-1gt.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`69b492c`](https://github.com/sase-org/sase/commit/69b492c27848b08c25c10cadb2045825a57a3e52) | fix(pager,ace): handle Textual 8.2 theme removal and childless frontmatter mount | [sase-1gt.2](sase-1gt.2.md) | 2026-10-05 12:48:50 EDT |

# Bead: sase-1if.7 — Commands in the Updates tab and plugin detail

[Bead Pages](../README.md) / [sase-1if](README.md) / sase-1if.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0n.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0n.linker.w0.md) · **Assignee:** `sase-1if.7` · **Size:** medium
**Created:** 2026-10-08 15:26:26 EDT · **Closed:** 2026-10-09 13:12:33 EDT
**Plan:** [202610/plugin\_commands.md](https://github.com/sase-org/sase--plans/blob/main/202610/plugin_commands.md)

## Description

updates-tab: render the command chip in Updates rows, the shared detail panel, install and uninstall confirmations, and the post-install toast receipt, then refresh the affected PNG goldens.

## Notes

[2026-10-09T17:12:33Z · sase-1if.7--1] Updates-tab command chips done: row chips, detail Commands row, install/uninstall/update confirm lines plus collision warnings, v4 receipt codec with lifecycle effects, toast command lines, lazy declared-preview worker, 3 new PNG goldens. Verified: just fmt, ruff, mypy, symvision, validate, validate-committed-plans clean; 22 new tests in test_updates_tab_commands.py pass; 85 related tests pass; just test-visual 30 passed check-clean. Full just check/test-scoped exceeded host time budgets after the 25min sase-core rebuild (monitor hrybs31cfn2c timed out at 1h); no failures observed, lint stages all passed in that run.

## Dependencies

- **Blocks:** [sase-1if.10](sase-1if.10.md) ◐ · ⧖ 2026-10-08
- **Depends on:** [sase-1if.6](sase-1if.6.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1if.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1if.7.md) | [sase-1if.7](sase-1if.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f0c732e`](https://github.com/sase-org/sase/commit/f0c732e70d07e2849556c487f0ff339b7bc9b984) | feat(sase-1if.7): render plugin commands across Updates tab, detail panel, confirms, and toast | [sase-1if.7](sase-1if.7.md) | 2026-10-09 13:14:31 EDT |

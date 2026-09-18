# Bead: sase-12z.2 — Compare candidates and safely apply screenshot changes

[Bead Pages](../README.md) / [sase-12z](README.md) / sase-12z.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mx](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mx.md) · **Assignee:** `sase-12z.2` · **Size:** medium
**Created:** 2026-09-18 10:39:52 EDT · **Closed:** 2026-09-18 13:32:47 EDT
**Plan:** [202609/fix\_tui\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_tui_screenshots.md)

## Description

maintenance-runner: implement tools/fix_tui_screenshots with explicit check mode, governed pytest execution, exact pixel comparison, bounded stability verification, conservative orphan handling, recoverable application, and tests for failures and unchanged golden trees.

## Notes

[2026-09-18T17:32:47Z · sase-12z.2--4] implemented tools/fix_tui_screenshots with explicit check mode, governed visual pytest via tools/run_pytest visual, exact pixel comparison (encoding-only is a no-op; dimension mismatch is an update), bounded verification pass, conservative stale handling, recoverable apply with journal; CLI/apply tests 37 passed, visual image tests 3 passed, just check green after rust-install restored select_remaining_commit_obligations so scoped bindings/finalizer tests pass. No --epic-symbol leftovers. Public Just/CI/docs integration is later phases.

## Dependencies

- **Depends on:** [sase-12z.1](sase-12z.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-12z.3](sase-12z.3.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12z.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12z.2.md) | [sase-12z.2](sase-12z.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9243c0b`](https://github.com/sase-org/sase/commit/9243c0bdd7563d2271de57833084e721fec4958e) | feat(visual): add screenshot golden maintenance runner | [sase-12z.2](sase-12z.2.md) | 2026-09-18 13:34:39 EDT |

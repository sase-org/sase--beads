# Bead: sase-wm.3 — The run-in-terminal valve for TTY-only blockers

[Bead Pages](../README.md) / [sase-wm](README.md) / sase-wm.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.e.md) · **Assignee:** `sase-wm.3` · **Size:** small
**Created:** 2026-09-04 11:59:00 EDT · **Closed:** 2026-09-04 22:32:21 EDT
**Plan:** [202609/projects\_tab\_init.md](https://github.com/sase-org/sase--plans/blob/main/202609/projects_tab_init.md)

## Description

valve: when the plan reports TTY-only blockers, offer a "Run in terminal" button that suspends the TUI into interactive `sase init` for the blocked subset, handles unsupported suspend, and reloads on return without ever reporting held projects as initialized.

## Notes

[2026-09-05T02:32:21Z · sase-wm.3] Auto-closed by `sase stitch create` after create_commit landed c018b7498 ("feat(ace): add run-in-terminal valve for tty-blocked init plans"). No verification is implied by this note. Reopen with `sase bead open sase-wm.3`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-wm.2](sase-wm.2.md) ✓ · ⧖ 2026-09-04
- **Blocks:** [sase-wm.4](sase-wm.4.md) ✓ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wm.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wm.3/README.md) | [sase-wm.3](sase-wm.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c018b74`](https://github.com/sase-org/sase/commit/c018b74987ac18c8ebd34be720a1391db8dc3824) | feat(ace): add run-in-terminal valve for tty-blocked init plans | [sase-wm.3](sase-wm.3.md) | 2026-09-04 22:31:22 EDT |

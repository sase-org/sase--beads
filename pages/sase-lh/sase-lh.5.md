# Bead: sase-lh.5 — Rename the ACE Tasks pane and Admin Center tab identifier to procs

[Bead Pages](../README.md) / [sase-lh](README.md) / sase-lh.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.000](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.000.md) · **Assignee:** `sase-lh.5` · **Size:** medium
**Created:** 2026-08-13 17:20:21 EDT
**Plan:** [202608/background\_tasks\_to\_procs.md](https://github.com/sase-org/sase--plans/blob/main/202608/background_tasks_to_procs.md)

## Description

tui-pane: rename the `tasks_pane*` and `tasks_store_rows` modules and `TasksPane` to their proc spellings, move the Admin Center tab identifier from `tasks` to `procs` with persisted-state migration, and rename the `#tasks-*` DOM ids and their `styles.tcss` selectors, without changing displayed text.

## Dependencies

- **Depends on:** [sase-lh.2](sase-lh.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-lh.6](sase-lh.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lh.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.5/README.md) | [sase-lh.5](sase-lh.5.md) | 0 |

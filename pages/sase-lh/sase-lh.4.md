# Bead: sase-lh.4 — Rename the TUI tracked-task runtime to procs

[Bead Pages](../README.md) / [sase-lh](README.md) / sase-lh.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.000](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.000.md) · **Assignee:** `sase-lh.4` · **Size:** medium
**Created:** 2026-08-13 17:20:03 EDT
**Plan:** [202608/background\_tasks\_to\_procs.md](https://github.com/sase-org/sase--plans/blob/main/202608/background_tasks_to_procs.md)

## Description

tui-runtime: rename `task_queue.py`, `task_mirror.py`, `task_subprocess.py`, `task_actions.py`, `widgets/task_indicator.py`, and the `_*_tasks.py` action mixins to their proc spellings, rename `TaskQueue`/`TaskMirror`/`TaskReporter`/ `TrackedTask*`/`_submit_tracked_task` and every call site, without changing displayed text.

## Dependencies

- **Depends on:** [sase-lh.2](sase-lh.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-lh.6](sase-lh.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lh.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.4/README.md) | [sase-lh.4](sase-lh.4.md) | 0 |

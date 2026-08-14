# Bead: sase-lh.4 — Rename the TUI tracked-task runtime to procs

[Bead Pages](../README.md) / [sase-lh](README.md) / sase-lh.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.000](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.000.md) · **Assignee:** `sase-lh.4` · **Size:** medium
**Created:** 2026-08-13 17:20:03 EDT · **Closed:** 2026-08-13 21:20:30 EDT
**Plan:** [202608/background\_tasks\_to\_procs.md](https://github.com/sase-org/sase--plans/blob/main/202608/background_tasks_to_procs.md)

## Description

tui-runtime: rename `task_queue.py`, `task_mirror.py`, `task_subprocess.py`, `task_actions.py`, `widgets/task_indicator.py`, and the `_*_tasks.py` action mixins to their proc spellings, rename `TaskQueue`/`TaskMirror`/`TaskReporter`/ `TrackedTask*`/`_submit_tracked_task` and every call site, without changing displayed text.

## Notes

[2026-08-14T01:20:30Z · sase-lh.4] Renamed TUI tracked-task runtime modules/symbols to proc spellings and updated call sites/tests. Verified with just install, just fmt, just check, just test-visual, and rename sweeps leaving only the intentional retired task_queue key.

[2026-08-14T01:21:49Z · sase-lh.4] Renamed TUI tracked-task runtime internals to proc naming; verified just install, just fmt, just check, just test-visual; final sweeps leave only intentional retired task_queue key references.

## Dependencies

- **Depends on:** [sase-lh.2](sase-lh.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-lh.6](sase-lh.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lh.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.4/README.md) | [sase-lh.4](sase-lh.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5ec9262`](https://github.com/sase-org/sase/commit/5ec9262274d8d7a4e8793117d91807598963004e) | refactor(tui): rename tracked task runtime to procs | [sase-lh.4](sase-lh.4.md) | 2026-08-13 21:24:42 EDT |

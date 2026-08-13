# Bead: sase-lh.2 — Move the Python package to sase.procs and migrate on-disk state and config

[Bead Pages](../README.md) / [sase-lh](README.md) / sase-lh.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.000](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.000.md) · **Assignee:** `sase-lh.2` · **Size:** medium
**Created:** 2026-08-13 17:19:15 EDT
**Plan:** [202608/background\_tasks\_to\_procs.md](https://github.com/sase-org/sase--plans/blob/main/202608/background_tasks_to_procs.md)

## Description

store: `git mv src/sase/tasks src/sase/procs`, rename `BackgroundTask` to `Proc` and `task_id` to `proc_id` throughout, move the store to `~/.sase/procs/procs.jsonl` with a marker-guarded one-shot migration, rename the `tasks.history_limit` config key to `procs.history_limit` with the legacy key still honored, and update `tools/validate_sase_core_rs` plus the monitor cross-references.

## Dependencies

- **Depends on:** [sase-lh.1](sase-lh.1.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-lh.3](sase-lh.3.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-lh.4](sase-lh.4.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-lh.5](sase-lh.5.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lh.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.2/README.md) | [sase-lh.2](sase-lh.2.md) | 0 |

# Bead: sase-lh.2 — Move the Python package to sase.procs and migrate on-disk state and config

[Bead Pages](../README.md) / [sase-lh](README.md) / sase-lh.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.000](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.000.md) · **Assignee:** `sase-lh.2` · **Size:** medium
**Created:** 2026-08-13 17:19:15 EDT · **Closed:** 2026-08-13 20:11:06 EDT
**Plan:** [202608/background\_tasks\_to\_procs.md](https://github.com/sase-org/sase--plans/blob/main/202608/background_tasks_to_procs.md)

## Description

store: `git mv src/sase/tasks src/sase/procs`, rename `BackgroundTask` to `Proc` and `task_id` to `proc_id` throughout, move the store to `~/.sase/procs/procs.jsonl` with a marker-guarded one-shot migration, rename the `tasks.history_limit` config key to `procs.history_limit` with the legacy key still honored, and update `tools/validate_sase_core_rs` plus the monitor cross-references.

## Notes

[2026-08-14T00:10:42Z · sase-lh.2] PROPOSED FOLLOW-UP: The scoped test lane is flaky under heavy concurrent workspace load (multiple sibling sase_<N> workspaces running just check/check-full simultaneously, load avg ~45-50). Two consecutive just check runs each hit exactly one unrelated, non-reproducing failure (tests/monitor/test_monitor_supervise.py::test_run_supervisor_escalates_term_ignoring_chatty_child, then tests/ace/tui/modals/test_snippet_name_modal.py::test_derived_only_collision_returns_composed_template); both pass standalone and touch files untouched by this phase. Worth investigating whether the scoped/full test runner needs stronger isolation or resource limits under multi-agent contention.

[2026-08-14T00:11:06Z · sase-lh.2] Moved src/sase/tasks to src/sase/procs (git mv), renamed BackgroundTask->Proc/task_id->proc_id and all facade symbols throughout, added src/sase/procs/_migration.py for the marker-guarded on-disk tasks->procs migration (with a running-proc symlink for live log writers), renamed the config key to procs.history_limit with tasks.history_limit as a deprecated legacy alias, updated tools/validate_sase_core_rs and all call sites (bead, main, ace/tui, monitor docstrings). Fixed 5 regressions surfaced by just check: two mobile/TUI-triage tests stubbing Proc with a stale task_id attribute, validate_sase_core_rs_tool's test still asserting the legacy binding names, a new untracked directory-operation audit gate hit for procs/_migration.py:_perform_migration (added a reviewed exemption), and a labels-phase-scope leak where the ProcRefError message text had already flipped to proc wording inconsistently across tests -- reverted to task wording (and fixed test_procs_facade.py's own assertion) since displayed/status text is explicitly the labels phase's job. Verified: just install succeeded against the linked sase-core build; just check passed clean end-to-end (all lint gates + full escalated test suite, 29766+ tests) on the final run after fixes, following two earlier full runs that each hit exactly one unrelated non-reproducing flaky test (confirmed passing standalone, in files untouched by this phase) under heavy concurrent multi-workspace load.

## Dependencies

- **Depends on:** [sase-lh.1](sase-lh.1.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-lh.3](sase-lh.3.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-lh.4](sase-lh.4.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-lh.5](sase-lh.5.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lh.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.2/README.md) | [sase-lh.2](sase-lh.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`62fb941`](https://github.com/sase-org/sase/commit/62fb94129662db94663cf5156c09e87223af4068) | refactor(procs): move sase.tasks to sase.procs and migrate on-disk state | [sase-lh.2](sase-lh.2.md) | 2026-08-13 20:11:56 EDT |

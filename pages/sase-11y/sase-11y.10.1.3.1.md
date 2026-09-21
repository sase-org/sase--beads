# Bead: sase-11y.10.1.3.1 — Retire the AXE watchdogs and alias sase axe to sase scheduler

[Bead Pages](../README.md) / [sase-11y.10.1.3](sase-11y.10.1.3.md) / sase-11y.10.1.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.md) · **Assignee:** `sase-11y.10.1.3.1.land`
**Created:** 2026-09-20 21:17:53 EDT · **Closed:** 2026-09-21 02:58:02 EDT
**Plan:** [202609/axe\_cli\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_cli_sunset.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/axe_cli_sunset.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/axe_cli_sunset.md

<!-- sase:links:end -->

## Description

The sase service host is the only thing that starts, restarts, or stops the scheduler from a CLI path: the ensure watchdog and its systemd timer are gone, no agent wait heals axe, the axe-start systemd scope wrapper and its doctor check are gone, `sase update` / `sase flag` / `sase plugin` restart the `scheduler` service proc instead of the AXE daemon, `sase axe start|stop|restart|status` is a documented alias of `sase scheduler`, and the direct AXE restart machinery that those paths kept alive is deleted.

## Notes

[2026-09-21T04:06:04Z · toobig-5q.loading_apply.0] DISCOVERED ISSUE (2026-09-21, master 44577fb8f9, found while verifying an unrelated file split): `just check` fails at lint (symvision) with 'Unused public functions/classes': AxeDesiredState (src/sase/axe/desired_state.py), lifecycle_journal_path and read_recent_successful_starts (src/sase/axe/lifecycle_journal.py). Reproduced on a clean HEAD via git stash, so it is not caused by that diff; sase-14t.4 also reported these names in passing as a PROPOSED FOLLOW-UP.

CAUSE: their only non-test consumers in src/ were src/sase/axe/_ensure_runtime.py and src/sase/axe/ensure.py, both deleted by 0806937467 (sase-11y.10.1.3.1.1, 'delete the axe ensure watchdog'). git grep at 0806937467^ shows those consumers; at HEAD each symbol appears only in its own module. AxeDesiredState and lifecycle_journal_path are still used inside their own files (desired_state.py:34-59; lifecycle_journal.py:61,81) so per symvision.md they should become private; read_recent_successful_starts has no remaining reference except its __all__ entry, so it is dead unless a later phase consumes it. Plausibly owned by sase-11y.10.1.3.1.5 (delete the AXE restart machinery the alias orphaned).

IMPACT: until resolved, every agent's just check ends red at lint (symvision) regardless of their own diff.

[2026-09-21T06:58:02Z · sase-11y.10.1.3.1.land] Verified all 5 phases against source and commits 080693746, d65316234, c833ff3e5, 0508f288f, and b87c8e3ee. The ensure watchdog, its timer, the wait-loop heal, and the ensure lock are gone, along with the three heal notifications, systemd_scope.py and its doctor check, and the orchestrator_session_scope issue. restart_after_update now calls restart_service_proc(scheduler), and UPDATE_JSON_SCHEMA_VERSION is 4. sase axe start|stop|restart|status delegate to handle_scheduler_command, the detached daemon argv is `sase scheduler run`, and the alias is named in both helps. _process_restart, _restart_events, restart_render, and status_render are deleted and their re-exports pruned. `sase axe ensure` is rejected.

The landing commit finishes epic-caused leftovers, fixed inline because each was small:
(1) Symvision. The epic's own note and sase-150 reported that 080693746 orphaned 3 symbols. AxeDesiredState and lifecycle_journal_path are now private; read_recent_successful_starts and its assertion are deleted.
(2) tests/main/test_update_command_entry.py pinned schema version 3. d65316234 bumped it to 4, so the pin is now 4 (sase-11y.10.1.3.1.2 follow-up #1).
(3) Three wedged-lock and stop messages told users to run `sase axe stop --force`, a flag axe-alias removed (sase-11y.10.1.3.1.4 follow-up). They now point at `sase scheduler restart`. The unreachable force branch is deleted: _force_kill_matching_axe_processes and its ps matchers (which matched ` axe start `, no longer the daemon argv) and AxeStopResult.force and .force_killed_processes.
(4) notify_axe_restart_failed lost its only producer when b87c8e3ee deleted _process_restart.py. It is deleted, along with its export.
(5) The sase axe restart/start/status/stop help text still described the deleted AXE behavior ("verify fresh worker heartbeats", "whole-system AXE health snapshot"). It now names the scheduler alias, and cli_spec.json is regenerated.
(6) update_handler_live's restart-skip reasons now say scheduler.
Linked plugin repos reference none of the removed symbols.

Integration: none of the non-epic commits since the epic started (a34db565b..42acc2979) touch AXE lifecycle, update restart, or the scheduler, and a whole-tree grep finds no remaining references to the removed surface outside docs, which sase-11y.10.1.5 owns.

Verification: sase tool run check. Every lint gate is green except symvision, which reports only bead_touch_glyph and ordered_bead_verb_chips. Those come from sase-14j.5 (2b3b37e89) and are already a DISCOVERED ISSUE on sase-14j, so this epic leaves them alone. toobig, validate, and committed-plans pass. just test-scoped: 15374 passed, 1 failed. The failure is the known flake test_usage_only_changes_do_not_move_control_row, which failed 1 of 8 runs on clean HEAD (+1 on sase-14z).

Follow-up outcomes:
- .2 #1 schema pin: fixed here (epic-caused).
- .2 #2 plugins batch-path flake: not epic-caused (the test stubs _restart_tui) and did not reproduce in 5 runs. Filed as sase-154.
- .4 --force advice: fixed here.
- .5 #1 status --full: filed as feature sase-153. It was out of scope because the plan deleted and did not add.
- .5 #2 chat_install direct start: filed as bug sase-152, related to sase-14x and sase-11y.10.1.
Also +1'd sase-14o (bead-store test).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.3.1.land/README.md) | [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`103db4b`](https://github.com/sase-org/sase/commit/103db4bfa8af0a114efecf109a02b8298701f2a6) | refactor(axe): retire leftovers of the AXE CLI sunset epic | [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) | 2026-09-21 03:02:19 EDT |
| sase--plans | [`sase--plans@d798718`](https://github.com/sase-org/sase--plans/commit/d798718ddd828de453b24406cac4d67e1ba7240f) | chore(plans): mark axe\_cli\_sunset done | [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) | 2026-09-21 03:06:02 EDT |

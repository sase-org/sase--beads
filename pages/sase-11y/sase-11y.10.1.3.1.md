# Bead: sase-11y.10.1.3.1 — Retire the AXE watchdogs and alias sase axe to sase scheduler

[Bead Pages](../README.md) / [sase-11y.10.1.3](sase-11y.10.1.3.md) / sase-11y.10.1.3.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.md) · **Assignee:** `sase-11y.10.1.3.1.land`
**Created:** 2026-09-20 21:17:53 EDT
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

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.3.1.land/README.md) | [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) | 0 |

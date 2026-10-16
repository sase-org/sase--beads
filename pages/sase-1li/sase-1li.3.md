# Bead: sase-1li.3 — Prompt templates, docs, and memory

[Bead Pages](../README.md) / [sase-1li](README.md) / sase-1li.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4n.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4n.linker.w0.md) · **Assignee:** `sase-1li.3` · **Size:** small
**Created:** 2026-10-16 13:03:53 EDT · **Closed:** 2026-10-16 18:04:25 EDT
**Plan:** [202610/closed\_bead\_launch\_attach.md](https://github.com/sase-org/sase--plans/blob/main/202610/closed_bead_launch_attach.md)

## Previously Closed

> ↺ Closed 2026-10-16T20:52:30Z · done
>
> (none)
>
> Reopened 2026-10-16T21:56:54Z by a status update

## Description

guidance: add the closed-bead sentence to the bd/work_phase_bead and bd/work_task prompts, document the attach and closed_while_queued rules in the bead claim lifecycle, %id, and ,x docs, correct the generated sase_beads memory, and record the out-of-scope follow-ups for the land agent.

## Notes

[2026-10-16T20:10:16Z · sase-1li.3] PROPOSED FOLLOW-UP: Fix premature closes at the source — move bd/work_phase_bead and bd/work_task closes behind the finalizer post-commit bead_action: close (close_assigned_bead_after_commit in src/sase/workflows/commit/bead_hooks.py) so failed commits stay in_progress, which ,x already handles. Medium. Root cause of most closed-bead relaunches (research case sase-xe.6).

[2026-10-16T20:10:24Z · sase-1li.3] PROPOSED FOLLOW-UP: ,x banner and sase agent restart preview hint (src/sase/agent/_restart_preview.py) saying the bead is closed and the relaunch will attach.

[2026-10-16T20:10:26Z · sase-1li.3] PROPOSED FOLLOW-UP: Non-failure stood-down outcome for closed_while_queued instead of a red failed agent.

[2026-10-16T20:52:19Z · sase-1li.3--1] PROPOSED FOLLOW-UP: TUI app import budget at cap on clean HEAD — tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget fails with 3520 modules against the 3520 strict-< cap; tools/tui_import_closure --diff vs origin/master is +0 from this phase (HEAD a9701c36e6). Last cap move was sase-1lc.8.3. Needs an owner to attribute the extra module and defer or raise with a named commit.

[2026-10-16T20:52:24Z · sase-1li.3--1] PROPOSED FOLLOW-UP: SQLITE_BUSY flake in tests/tool/test_settlement_retention.py::test_supervisor_sigterm_records_stop_intent_worker_settles_stop (tool run store is busy: database is locked); first_seen earlier, touched=false, same class as sase-18t. Reproduces under the full-lane just check; not caused by this guidance phase.

[2026-10-16T20:52:30Z · sase-1li.3--1] Guidance landed: closed-bead attach sentence in bd/work_phase_bead and bd/work_task, Bead Claim Lifecycle attach + closed_while_queued docs, %id bead= and ,x/restart docs, generated sase_beads memory via the init template, and the three plan follow-ups plus two pre-existing just-check failures recorded. just check (tool run 08b068d595c66dc15469c69de3b1f275) had 2 NEW on clean HEAD (TUI import 3520/3520 +0 from this phase; SQLITE_BUSY settlement flake, sase-18t class) and 1 KNOWN; epic-symbols empty.

[2026-10-16T21:56:55Z · bryanbugyi34@gmail.com] I'm not sure if this work is completed or not but the agent that was attempting to work on it failed.

[2026-10-16T22:04:25Z · sase-1li.3] Verified existing phase implementation: both bead work prompt templates cover closed-bead attach; lifecycle, %id, and restart docs describe attach and closed_while_queued; generated sase_beads memory matches its authorized template. Existing phase notes record follow-ups and clean-base check failures. sase bead epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-1li.2](sase-1li.2.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1li.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1li.3.md) | [sase-1li.3](sase-1li.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4b000ca`](https://github.com/sase-org/sase/commit/4b000ca2c6a966966fe7819c2ef2c73e0191efb7) | docs(beads): document closed-bead launch attach in prompts and memory | [sase-1li.3](sase-1li.3.md) | 2026-10-16 17:28:15 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1li.3--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1li.3.md

<!-- sase:referenced-by:end -->

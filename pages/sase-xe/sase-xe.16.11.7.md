# Bead: sase-xe.16.11.7 — One Agents experience across machines

[Bead Pages](../README.md) / [sase-xe.16.11](sase-xe.16.11.md) / sase-xe.16.11.7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0hv` · **Assignee:** `sase-xe.16.11.7.land`
**Created:** 2026-09-09 15:49:25 EDT
**Plan:** [202609/unified\_agents\_across\_machines.md](https://github.com/sase-org/sase--plans/blob/main/202609/unified_agents_across_machines.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/unified_agents_across_machines.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/unified_agents_across_machines.md

<!-- sase:links:end -->

## Description

ACE presents one trustworthy Agents list across the local machine and every enrolled machine — with durable fleet-wide attention, explicit launch targets, and a Machines home — built on repaired Rust-owned fleet contracts and proven by live Athena-to-Apollo acceptance.

## Notes

[2026-09-11T11:07:52Z · 0j3--code] DISCOVERED ISSUE: During verification for the unrelated prose %if/%proc directive false-positive fix on 2026-09-11, just check stopped at lint (feature flags) after fmt, markdown fmt, keep-sorted, ruff, and mypy passed. tools/check_feature_flags reports: rule 8: live flag bead sase-z6 has no definition (key ace_unified_agents); created 2026-09-10T05:53:35Z by bbugyi200.athena.sase-xe.16.11.7.6. This is not a flake and not caused by my diff, which only touches xprompt directive parsing/tests plus the Rust typed-launch planner. It belongs here because this epic owns the unified Agents experience and phase .6 created the flag bead; no duplicate CI task was created.

[2026-09-11T11:33:19Z · 0j4--5] DISCOVERED ISSUE (corroboration): Independent reproduction during verification of the unrelated 202609/axe_restart_command.md plan (sase axe restart command implementation) on 2026-09-11. just check stopped at lint (feature flags) after fmt, markdown fmt, keep-sorted, ruff, and mypy all passed. tools/check_feature_flags reports the same: rule 8: live flag bead sase-z6 has no definition (key ace_unified_agents); created 2026-09-10T05:53:35Z by bbugyi200.athena.sase-xe.16.11.7.6. Diff under review only touches src/sase/axe/_restart_events.py, src/sase/axe/_process_restart.py, src/sase/axe/process.py, src/sase/axe/restart_render.py, src/sase/main/parser_ace.py, src/sase/main/axe_handler.py, tests/test_axe_restart*.py, docs/axe.md, docs/cli.md -- unrelated to this flag. Still reproducing ~1 day after the bead's creation, well past a normal cross-tree landing race window. No duplicate task bead created; corroborating the existing note #1 on this epic instead per sase_beads.md guidance.

[2026-09-14T12:19:51Z · sase-zn.9.land--2] DISCOVERED ISSUE: New full-parallel-lane flake in the Machines pane this epic's closed phase sase-xe.16.11.7.10 added: tests/ace/tui/test_machines_pane.py::test_status_check_is_user_triggered_and_records_observation failed once with KeyError 'apollo' at line 120 (pane._statuses['apollo'] missing after the status check settled) during the sase-zn.9 landing's just check-full test-cost lane on 2026-09-14 (monitor hx7zy0pk3ve8), then passed 3/3 isolated reruns on the same tree — classic fails-under-the-full-parallel-lane, passes-in-isolation. Credible mechanism in src/sase/ace/tui/modals/machines_pane.py:_handle_status_worker_state (lines 329-362): _checking_alias is cleared for ANY terminal worker state, but _statuses is recorded only on SUCCESS with a tuple result, so a CANCELLED/ERROR settle (or a lost result) under lane load releases the test's 'not pane._checking_alias' wait before any status was recorded. The landing diff (sase-zn.9) never touches this pane or test. No matching task bead exists (searched machines_pane/test_status_check and swept 1w of tasks); routed here per the active-epic branch instead of creating a task, since this epic owns the pane.

# Bead: sase-18d.7 — Complete Agents-tab x end-to-end regression coverage

[Bead Pages](../README.md) / [sase-18d](README.md) / sase-18d.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-18d.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-18d.land.md) · **Assignee:** `sase-18d.7.land`
**Created:** 2026-09-24 22:00:15 EDT · **Closed:** 2026-09-25 01:34:48 EDT
**Plan:** [202609/x\_kill\_e2e\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/x_kill_e2e_completion.md)

## Description

Exercise the sase-18d kill and dismissal contract through the real Agents tab, durable cleanup, disk reload, and process trees.

## Notes

[2026-09-25T05:34:48Z · sase-18d.7.land] LAND VERIFIED at master 02c4b029a. (1) Both phases closed and implemented. clan_race (ae34dba20): mounted-AceApp pilot harness tests/ace/tui/_agents_x_pilot_helpers.py plus test_agents_tab_x_clan_race_e2e.py (real x and confirm, on-disk agents, real process trees, a load parked between prep and apply, fleet reprojection, forced complete-history reload, durable payload). It fixed the epic-caused racing-load resurrection in _loading_compute.py/_loading_apply.py so the boundary keeps the worker's removal provenance, with component regressions in test_agents_tab_removal_tombstones.py. row_lifecycle (02c4b029a): test_agents_tab_x_row_lifecycle_e2e.py covers FAILED retry-backoff kill, FAILED twin, DONE finalizer untouched, x then immediate exit, and a fresh app instance. It fixed same-identity twin handling in _dismiss_persistence.agents_related_to_dismissal and _kill_termination.live_dismissed_agents, with two unit tests. Reviewed the diffs. The pilot, tombstone, durable-termination, terminate-processes and member-scope suites give 62/62 passed with sase-core-rs 0.34.73 (via just rust-install and .venv/bin/python). With the 0.34.71 wheel that uv run re-syncs to, all 7 pilots time out on 'unknown field agent_session' (a binding-floor issue, not an epic defect). (2) Integration: commits since the epic started (61f88ccd6, d2c2dd142, 7840592c5, 696026157, fad9b5d03, plus a2ec65a1f/bde335de5 around the start) touch the command line, xprompt goldens, the agent-session docs rename and lint stragglers. None touches the kill/dismiss/loading paths or duplicates the harness; the epic tests pass on HEAD, so no integration change was needed. No epic-symbol entries. (3) Follow-ups: 7.1#1 (34 clean-tree failures): 373/374 of that reproducer set pass with the correct binding, so root cause is mostly the stale binding. Noted that on sase-18s, and the remaining node is a +1 on sase-14o. 7.1#2 (_agents_local_visible write-only, stale after clan x): predates sase-18d (2da11eb28), filed as sase-18x (small bug, ready). 7.2#1 (sase-core-rs floor below 0.34.73): DISCOVERED ISSUE note on active epic sase-17m, whose pin bump is 17m.9. 7.2#2 and 7.1#3 (check blockers): declined, already tracked by sase-18q/sase-18r/sase-o7. 7.2#4 (mypy tools/smoke_sase_core_rs_tool_runs:75): declined, already fixed by 7840592c5.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18d.7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.7.land/README.md) | [sase-18d.7](sase-18d.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@a8f152f`](https://github.com/sase-org/sase--plans/commit/a8f152f1274f99385b54eef086db01d8646ae1bc) | docs(plans): mark sase-18d and sase-18d.7 x-kill plans done | [sase-18d.7](sase-18d.7.md) | 2026-09-25 01:39:43 EDT |

# Bead: sase-18d.3 — Verified process-tree termination in the durable cleanup proc

[Bead Pages](../README.md) / [sase-18d](README.md) / sase-18d.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ra](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ra.md) · **Assignee:** `sase-18d.3` · **Size:** medium
**Created:** 2026-09-24 16:28:32 EDT · **Closed:** 2026-09-24 19:04:04 EDT
**Plan:** [202609/x\_kill\_removal\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/x_kill_removal_reliability.md)

## Description

tree-kill: add a shared terminator that finds an agent's whole process set (process group, session, ppid tree, and inherited launch scratch key). It sends SIGTERM, escalates to SIGKILL, and verifies death. The durable persist-cleanup proc runs it before it releases workspaces or deletes artifacts. The TUI only sends the immediate SIGTERM. Also stop the in-flight guard from dropping whole batches.

## Notes

[2026-09-24T23:03:12Z · sase-18d.3] PROPOSED FOLLOW-UP: additive-dismissals must also cover the early dismissal publish — persist_single_kill_transaction and persist_bulk_kill_transaction now call save_dismissed_agents(snapshot) before terminating (persist_bulk_kill_side_effects takes publish_dismissal=False so it saves once); switch those two call sites to the add/remove API, and note the termination window (up to ~8s) widens the stale-snapshot race until they do.

[2026-09-24T23:03:29Z · sase-18d.3] PROPOSED FOLLOW-UP: read_process_registry (list_running_agents + proc store) runs once per terminate_agent_processes call that finds an escaped or ppid-only process, so a clan kill reads it once per member in parallel threads; cache it per terminate_agents batch if it shows up in persist-cleanup profiles.

[2026-09-24T23:03:43Z · sase-18d.3] PROPOSED FOLLOW-UP: master is red on gates unrelated to this epic (verified identical on a clean stash): mypy 15 errors in ace/tui/widgets/_agent_detail_{display,state}.py and ace/tui/command_line/{input,screen}.py; symvision unused private _dispatch_preview_source_summary; toobig widgets/decks/panel.py and tests/tool/test_settlement.py; test-waits tests/ace/tui/command_line/test_completion_popup.py:181; pyscripts Rule 2 on tests/ace/tui/visual; 62 scoped test failures, including 20 in test_agent_cleanup_facade.py that assert wire schema 4 while the rebuilt sase_core_rs reports 5 (core-wire in flight).

[2026-09-24T23:04:04Z · sase-18d.3] Added terminate_agent_processes (agent/user_kill.py + process_tree.py/process_registry.py): /proc discovery by pgid, sid, ppid tree and recorded SASE_LAUNCH_SCRATCH_KEY (now written to agent_meta.json), identity-pinned SIGTERM->rediscover->SIGKILL->verify, shields self/ancestors, registered supervisors stop via canonical stop, non-leader pid signals pid+tree, survivors recorded in the marker. Durable persist-cleanup kill/dismiss transactions publish the dismissal, terminate, then release workspaces/delete artifacts only for verified-dead agents (survivors keep claim, error names pids); dismissed live non-success-terminal rows get the safety net. TUI now sends only the immediate SIGTERM with a background-escalation fallback if the proc is rejected; in-flight guards drop only overlapping rows; sase agent kill/wipe/plan-reject use the terminator. Verified: real-process tests (same-group, own-group, setsid key-carrying orphan, SIGTERM-ignoring child, shielded/identity-mismatched/non-leader pids, transaction ordering, survivors) plus updated kill/dismiss tests pass; ruff/format/keep-sorted pass; scoped lane shows only the 62 failures that fail identically on a clean tree; epic-symbols: none.

## Dependencies

- **Depends on:** [sase-18d.2](sase-18d.2.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18d.4](sase-18d.4.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18d.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.3/README.md) | [sase-18d.3](sase-18d.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b7cfa06`](https://github.com/sase-org/sase/commit/b7cfa069cb45b421f4abc87ddb8b21bb15d71c05) | feat(agent): verified process-tree termination in the durable cleanup proc (sase-18d.3) | [sase-18d.3](sase-18d.3.md) | 2026-09-24 19:05:19 EDT |

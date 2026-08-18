# Bead: sase-p8.2 — Shared pending-handoff marker protocol

[Bead Pages](../README.md) / [sase-p8](README.md) / sase-p8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05f.md) · **Assignee:** `sase-p8.2` · **Size:** small
**Created:** 2026-08-17 19:01:00 EDT · **Closed:** 2026-08-17 20:55:16 EDT
**Plan:** [202608/agent\_pipe.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_pipe.md)

## Description

handoff: give the four marker-writing CLI hand-offs one guard/write/kill helper and one marker registry, and register the pipe marker there.

## Notes

[2026-08-17T23:52:40Z · sase-p8.2] Implemented shared pending-handoff registry + guard/write helper. Named PLAN/QUESTIONS/MONITOR/PIPE markers; PENDING_HANDOFF_MARKERS is derived from them. write_pending_handoff_marker stamps timestamp, writes atomically, fsyncs; handoff_guard refuses missing SASE_AGENT/SASE_ARTIFACTS_DIR and a second marker in one turn. Migrated questions, plan propose, and monitor writers. SIGTERM non-monitor set now includes pipe. Re-keyed stale sase-p1.2 epic-symbols to sase-p1 so just check is not red. Pulse-mtime test now deletes the consumed marker between proposes.

[2026-08-18T00:54:42Z · sase-p8.2--2] PROPOSED FOLLOW-UP: Re-key stale sase-p2.2 --epic-symbol catalog APIs — sase-p2.2 closed at 2026-08-18T00:45:45Z leaving Justfile entries for EditorRepoMentionCatalog, EditorRepoMentionCatalogResult, RepoMentionSpan, editor_repo_mention_catalog_for_project, lookup_repo_mention, and scan_repo_mentions; those symbols still have no non-test consumers; parent sase-p2 and later phases sase-p2.3/sase-p2.4 are still open; just check-full dies at lint (symvision) with bead sase-p2.2 is closed.

[2026-08-18T00:55:16Z · sase-p8.2--2] Named PLAN/QUESTIONS/MONITOR/PIPE marker constants in pending_handoff.py; PENDING_HANDOFF_MARKERS is derived from them; monitor/handoff.py re-exports MONITOR_PENDING_MARKER. handoff_guard() and write_pending_handoff_marker() in pending_handoff_write.py stamp timestamp, write atomically, and fsync; guard messages name SASE_AGENT/SASE_ARTIFACTS_DIR; a second marker write in one turn raises PendingHandoffError. questions_command_handler and plan_propose_handler write through the helper; write_monitor_pending_marker keeps its record-shaped payload but writes through the helper. run_agent_runner_signals._NON_MONITOR_HANDOFF_MARKERS is derived from the registry so the pipe marker joins the SIGTERM claim-hold set. Pulse-mtime plan test unlinks the consumed marker between proposes. Verified: just install; 29 targeted pytest passed (test_pending_handoff, test_plan_command_handler, test_run_agent_runner_auto_dismiss) plus 10 related monitor/questions handoff tests; sase bead epic-symbols sase-p8.2 has no leftovers; just check-full lint gates passed (fmt, ruff, mypy, flags, pyscripts, test waits, changelog, patch/stitch, toobig, SASE validation, committed plans) except an unrelated stale sase-p2.2 --epic-symbol set after that phase closed; a prior 45m check-full passed every lint gate including symvision then timed out in the test suite.

[2026-08-18T00:56:30Z · sase-p8.2--2] Shared pending-handoff marker protocol: named PLAN/QUESTIONS/MONITOR/PIPE constants with PENDING_HANDOFF_MARKERS derived from them; handoff_guard() and write_pending_handoff_marker() (timestamp, atomic write, fsync; second write in one turn raises PendingHandoffError); questions/plan CLI writers plus write_monitor_pending_marker migrated onto the helper; _NON_MONITOR_HANDOFF_MARKERS derived from the registry so the pipe marker joins the SIGTERM claim-hold set; targeted pytest 29+10 passed; epic-symbols for this phase empty; earlier check-full passed every lint gate then timed out in the suite; latest check-full failed on unrelated stale sase-p2.2 --epic-symbol leftovers (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-p8.4](sase-p8.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p8.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p8.2.md) | [sase-p8.2](sase-p8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4edc0ab`](https://github.com/sase-org/sase/commit/4edc0ab235e29ac764df86bcbe9b65f095ad8a64) | feat(agent): share pending-handoff marker write protocol | [sase-p8.2](sase-p8.2.md) | 2026-08-17 20:58:37 EDT |

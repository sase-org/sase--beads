# Bead: sase-mq.4 — Approval and task launches off the primary checkout

[Bead Pages](../README.md) / [sase-mq](README.md) / sase-mq.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.035](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.035.md) · **Assignee:** `sase-mq.4` · **Size:** medium
**Created:** 2026-08-15 23:39:57 EDT · **Closed:** 2026-08-16 03:45:12 EDT
**Plan:** [202608/primary\_workspace\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/primary_workspace_ownership.md)

## Description

approval-launches: move approval-time plan archiving plus epic and task launch orchestration into durable operational workspace leases.

## Notes

[2026-08-16T07:44:09Z · sase-mq.4--1] PROPOSED FOLLOW-UP: Artifact-directory audit missing sase-mq.3 reset-replay site — tests/test_agent_artifact_directory_operation_audit.py fails because src/sase/workspace_provider/reset_replay.py:_clear_owned_paths is not in the reviewed-contexts whitelist (phase-3 leftover, not this approval-launches change).

[2026-08-16T07:44:30Z · sase-mq.4--1] PROPOSED FOLLOW-UP: Host-shared ~/.sase/procs/runtime contaminates CLI tests — gate CLI, gate conformance, and ops command tests read /home/bryan/.sase/procs/runtime/*/operation-request.json and fail when a concurrent agent left a run.launch sidecar (reproduces on clean master).

[2026-08-16T07:44:52Z · sase-mq.4--1] PROPOSED FOLLOW-UP: Full-suite config-cache tests ignore their token mock — just check-full-only failures in tests/test_config.py and tests/test_config_cache.py assert current_config_token() == ("token", 1) but observe a live token from this workspace; not in the launch/lease import graph.

[2026-08-16T07:45:12Z · sase-mq.4--1] Moved approval-time plan archiving plus epic/task launch off the primary checkout onto operational leases (archive via leased plans store + reset-and-replay; epic monitors start in lease.checkout_dir with transfer_claim_from_pid and release-on-pre-ack-failure; detached fallback is the same leased proc path; task triage submit_task_launch_task(project=...) acquires a task-launch lease). just check-full: 30776 passed; 93 failed + 45 errors. The one related miss (mobile task-triage still asserted cwd=) was updated to project= and 17 targeted launch/triage tests passed. Remaining failures are pre-existing/environmental (TUI vim containment, keybinding footer F-vs-f, gate/ops sidecar contamination from shared ~/.sase/procs/runtime, changespec onboarding, config-cache token mock) and reproduce without this diff. just check escalates on the Justfile symvision whitelist; fmt/ruff/mypy/symvision re-ran clean after the test fix. Parent sase-mq left open.

[2026-08-16T07:46:37Z · sase-mq.4--1] Verified approval-launches (sase-mq.4): epic/task launch, plan archive, and monitor claim-transfer now run on operational leases (project= + acquire/submit_via_lease, not primary cwd). just check-full: 30776 passed; 93 failed + 45 errors match the pre-existing environmental set (TUI vim/keybinding, gate/ops shared ~/.sase/procs/runtime, changespec onboarding, config-cache isolation). No new failures in epic_launch, task_launch, plan archive, monitor claim-transfer, or lease.py. Updated mobile triage assertion to project= launch API; 17 launch/triage tests passed. fmt/ruff/mypy/symvision clean.

## Dependencies

- **Depends on:** [sase-mq.3](sase-mq.3.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mq.7](sase-mq.7.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mq.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-mq.4.md) | [sase-mq.4](sase-mq.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1672858`](https://github.com/sase-org/sase/commit/16728587dd72a1e7c0ba817f380a09ba864e388b) | feat(workspace): run approval launches on operational leases | [sase-mq.4](sase-mq.4.md) | 2026-08-16 03:48:32 EDT |

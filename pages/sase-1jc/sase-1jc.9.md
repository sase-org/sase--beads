# Bead: sase-1jc.9 — Remove legacy monitor-start rollout paths

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.9` · **Size:** medium
**Created:** 2026-10-09 22:28:26 EDT · **Closed:** 2026-10-10 14:52:41 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

monitor-records: Follow phase 9 and the shared removal checklist. Retire monitor_continuation_records and close sase-102. Every new monitor uses versioned records and capture. Remove the selectable legacy writer/start path, while keeping existing monitor settlement and recovery governed by persisted protocol and sentinel fields. Exercise success/failure delivery, idempotency, recovery, and older persisted monitor records.

## Notes

[2026-10-10T18:52:12Z · sase-1jc.9] PROPOSED FOLLOW-UP: symvision flags 11 unused public functions in src/sase/ace/tui/modals/update_failure_geometry.py (from commit 217a5439f5); fails identically on the clean base tree, unrelated to monitor-records retirement

[2026-10-10T18:52:17Z · sase-1jc.9] PROPOSED FOLLOW-UP: tests/monitor/test_monitor_proc_facade.py::test_incident_save_chat_history_crash_recovers_completed_result fails identically on the clean base tree (proc status error instead of success); unrelated to monitor-records retirement

[2026-10-10T18:52:22Z · sase-1jc.9] PROPOSED FOLLOW-UP: Update sase/memory/macros.md to describe typed Proc launches as unconditional (epic decision macro_memory=no skips it here)

[2026-10-10T18:52:27Z · sase-1jc.9] PROPOSED FOLLOW-UP: Update sase/memory/tui_perf.md rule 14 to describe refresh tokens as unconditional (epic decision refresh_memory=no skips it here)

[2026-10-10T18:52:41Z · sase-1jc.9] Retired monitor_continuation_records (dossier sase-102 already closed with removal evidence). Every new monitor start unconditionally persists records_v1 protocol, frozen outcome policy, checkpoints and delivery state: removed the flag enum member/definition, new-start flag selection, legacy writer/start branch, versioned-controls rejection, capture env fallback, and MonitorLaunchContext.records_enabled. Retained persisted protocol/sentinel dispatch for settlement, follow-up, resume and recovery. Verified: ruff/mypy/fmt pass; tests/monitor + tests/continuation 554 passed; feature_flags, completion and capture suites pass; reworked rollout tests prove unconditional v1 starts plus legacy-protocol retention without flag overrides. Two check failures (symvision update_failure_geometry unused-publics; proc_facade incident crash test) reproduce identically on the clean base tree and are recorded as PROPOSED FOLLOW-UPs, as are the two epic-deferred memory-note updates. No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1jc.10](sase-1jc.10.md) ◐ · ⧖ 2026-10-09
- **Depends on:** [sase-1jc.8](sase-1jc.8.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.9/README.md) | [sase-1jc.9](sase-1jc.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1136a35`](https://github.com/sase-org/sase/commit/1136a35db29be9ba397d3fe12e7ceed7c04f0f40) | feat(monitors): retire monitor\_continuation\_records flag | [sase-1jc.9](sase-1jc.9.md) | 2026-10-10 14:54:32 EDT |

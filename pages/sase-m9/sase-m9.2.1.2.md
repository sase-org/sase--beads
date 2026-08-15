# Bead: sase-m9.2.1.2 — One detached proc service and supervisor

[Bead Pages](../README.md) / [sase-m9.2.1](sase-m9.2.1.md) / sase-m9.2.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.2.md) · **Assignee:** `sase-m9.2.1.2` · **Size:** medium
**Created:** 2026-08-15 06:14:48 EDT · **Closed:** 2026-08-15 07:34:11 EDT
**Plan:** [202608/unified\_proc\_shell\_platform\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_proc_shell_platform_1.md)

## Description

unified-proc-supervisor: introduce one typed Python proc submission request and service over the new Rust lifecycle, then promote the monitor bootstrap/supervision guarantees into the proc kernel: double-fork/reparenting, bounded acknowledgement and launch barrier, scrubbed child environment, boot-aware supervisor identity, direct persisted argv execution, merged binary-safe output, total and idle timeouts, process-group TERM-to-KILL escalation, stop intent, and reboot/pid-reuse/loss reconciliation. Move through settling and make settlement resumable and idempotent so the command, output, result envelope, workspace claim, artifacts, and follow-up policy are durable before terminal state. Keep Proc.log_path authoritative and only prune store-owned logs below the proc log root. Migrate ordinary proc CLI/API callers to the service, retaining compatibility reconciliation for already-running legacy rows and removing the weaker supervisor only after focused crash-boundary tests pass.

## Notes

[2026-08-15T11:31:54Z · sase-m9.2.1.2] PROPOSED FOLLOW-UP: 116 unrelated CLI/TUI tests fail on this tree because captured stdout now includes Rich ANSI bold around numbers and brackets (smallest repro: tests/test_output.py::test_escape_markup_in_log_fn). Not caused by the proc supervisor; just check escalated to the full suite via core-identity-changed.

[2026-08-15T11:32:49Z · sase-m9.2.1.2] PROPOSED FOLLOW-UP: just check reports core-identity-changed / blocked_unpublished because sase-core-rs==0.27.2 does not yet contain reserve_proc, claim_proc_supervisor, request_proc_stop, begin_proc_settlement, or finish_proc (first appear in unpublished 6d7000a). Land should publish a core release and raise the Python floor.

[2026-08-15T11:34:11Z · sase-m9.2.1.2] Implemented the typed ProcSubmitRequest service over Rust reserve/claim/stop/settle/finish, promoted monitor bootstrap (double-fork, ack, launch barrier, env scrub, boot-aware identity, argv exec, binary-safe logs, timeouts, TERM-to-KILL, stop intent, reboot/pid-reuse reconcile, resumable settlement) into the proc kernel, migrated ordinary CLI/API submit/kill/reconcile, kept legacy row compatibility via legacy_supervisor, and verified with just install, focused proc/CLI suites, just check lint, and the escalated full pytest lane (30110 passed; 116 unrelated Rich-ANSI CLI failures recorded as follow-up).

[2026-08-15T11:36:02Z · sase-m9.2.1.2] Implemented the typed ProcSubmitRequest service over Rust reserve/claim/stop/settle/finish, promoted monitor bootstrap (double-fork, ack, launch barrier, env scrub, boot-aware identity, argv exec, binary-safe logs, timeouts, TERM-to-KILL, stop intent, reboot/pid-reuse reconcile, resumable settlement) into the proc kernel, migrated ordinary CLI/API submit/kill/reconcile, kept legacy row compatibility via legacy_supervisor, and verified with just install, focused proc/CLI suites, just check lint, and the escalated full pytest lane (30110 passed; 116 unrelated Rich-ANSI CLI failures recorded as follow-up).

## Dependencies

- **Depends on:** [sase-m9.2.1.1](sase-m9.2.1.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.2.1.3](sase-m9.2.1.3.md) ◐ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.2.1.4](sase-m9.2.1.4.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.2/README.md) | [sase-m9.2.1.2](sase-m9.2.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`152268b`](https://github.com/sase-org/sase/commit/152268b597d070c653fe022e88c9370352e07a08) | feat(procs): route submits through one typed supervisor service | [sase-m9.2.1.2](sase-m9.2.1.2.md) | 2026-08-15 07:37:40 EDT |

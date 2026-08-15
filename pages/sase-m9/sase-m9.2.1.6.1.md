# Bead: sase-m9.2.1.6.1 — Make crash-boundary settlement recovery deterministic

[Bead Pages](../README.md) / [sase-m9.2.1.6](sase-m9.2.1.6.md) / sase-m9.2.1.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.2.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.2.1.land.md) · **Assignee:** `sase-m9.2.1.6.1` · **Size:** medium
**Created:** 2026-08-15 10:21:02 EDT · **Closed:** 2026-08-15 11:24:19 EDT
**Plan:** [202608/finish\_unified\_proc\_shell\_platform.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_unified_proc_shell_platform.md)

## Description

stabilize-settlement-recovery: root-cause and fix the reproducible race in tests/test_procs_service.py::test_settlement_resumes_after_an_injected_crash. Current master 6683d4bcc fails on the second focused invocation after the injected supervisor exits at output_closed: reconcile_running_procs can leave the row nonterminal until wait_for_proc times out. Inspect supervisor process identity, zombie/reparenting behavior, settling ownership, and reconciliation timing rather than weakening the timeout. Preserve the contract that a dead supervisor is detected, every settlement checkpoint resumes idempotently, and the row reaches a durable terminal state. Add a deterministic regression that exercises the actual race and stress every injected settlement checkpoint repeatedly. Run just install, focused proc service/supervisor/settlement suites, and just check. Record any unrelated failure as PROPOSED FOLLOW-UP on this phase instead of creating a task.

## Notes

[2026-08-15T15:24:19Z · sase-m9.2.1.6.1] Implemented wait_for_proc proc-shell reconciliation retry for stale active rows; verified just install, focused settlement regressions including all checkpoints x3, proc service/supervisor/runner/facade/migration/names suites (82 passed), 20 consecutive output_closed focused invocations, and just check passed; known core-floor advisory remains sibling phase scope.

[2026-08-15T15:27:49Z · sase-m9.2.1.6.1] Verified just install; focused settlement regressions; proc service/supervisor/runner/facade/migration/names suites (82 passed); original output_closed crash test passed 20 consecutive focused runs; just check passed.

## Dependencies

- **Blocks:** [sase-m9.2.1.6.3](sase-m9.2.1.6.3.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.2.1.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.6.1/README.md) | [sase-m9.2.1.6.1](sase-m9.2.1.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ffce3c8`](https://github.com/sase-org/sase/commit/ffce3c842846352f6b39e66066fdd30aaf9cd193) | fix(procs): recover proc-shell settlement while waiting | [sase-m9.2.1.6.1](sase-m9.2.1.6.1.md) | 2026-08-15 11:28:41 EDT |

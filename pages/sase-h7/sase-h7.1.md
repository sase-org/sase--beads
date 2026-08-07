# Bead: sase-h7.1 — Diagnosable input failures and non-destructive retry

[Bead Pages](../README.md) / [sase-h7](README.md) / sase-h7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v2/README.md) · **Assignee:** `sase-h7.1` · **Size:** medium
**Created:** 2026-08-07 17:06:39 EDT · **Closed:** 2026-08-07 17:38:33 EDT
**Plan:** [202608/gate\_input\_collection.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_collection.md)

## Description

executor-integrity: move gate input-schema validation inside the error-recording path, bound input size and depth, and add a per-attempt execution journal so a partially executed AND branch can be resumed or restarted deliberately instead of silently re-running its completed commands.

## Notes

[2026-08-07T21:38:02Z · sase-h7.1] PROPOSED FOLLOW-UP: journal.jsonl option_completed records store the raw command result (resume replay needs it) — inputs-core secret redaction must cover results too, since a command that echoes its stdin into stdout puts submitted input into durable audit data.

[2026-08-07T21:38:15Z · sase-h7.1] PROPOSED FOLLOW-UP: journal._read_journal_events is private because this phase has no non-test consumer for it — surface-input (sase-h7.10) should make it public when it adds the journal attempts tab and the wait --json operations key.

[2026-08-07T21:38:33Z · sase-h7.1] executor-integrity landed: input-schema/bounds/feedback/adapter rejections now record to errors/ via _recorded_rejection; new input_bounds.py enforces 64 KiB / depth 16 / 128 props / 512 items as input_too_large; new journal.py appends per-attempt journal.jsonl records (digest-only input) under .response.lock; execute_gate_selection gains retry='resume'|'restart' with partial_attempt / no_partial_attempt errors and attempt_superseded on changed input; ACE GateSubmission gains retry and _GateTaskOutcome gains a _PartialAttempt variant; idempotency expectation documented on GateAdapter and execute_gate_selection. Verified: new tests/test_gate_executor_integrity.py (11 tests) all pass, updated test_notification_gate_execution.py for the new feedback-rejection error record, and 'just check' passed with its scoped lane escalated to the full suite (27074 passed).

[2026-08-07T21:39:07Z · sase-h7.1] Verified: executor-integrity phase — recorded rejections for all pre-option gate failures, bounded input checks, execution journal, deliberate retry (resume/restart), idempotency docs; 11 new tests in tests/test_gate_executor_integrity.py; just check passed with full suite (27,074 passed).

## Dependencies

- **Blocks:** [sase-h7.4](sase-h7.4.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.1/README.md) | [sase-h7.1](sase-h7.1.md) | 0 |

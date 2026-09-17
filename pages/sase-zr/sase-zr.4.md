# Bead: sase-zr.4 — Decouple Telegram acknowledgements and cleanup from gate execution

[Bead Pages](../README.md) / [sase-zr](README.md) / sase-zr.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0js` · **Assignee:** `sase-zr.4` · **Size:** medium
**Created:** 2026-09-12 05:06:17 EDT · **Closed:** 2026-09-14 09:39:55 EDT
**Plan:** [202609/prompt\_gate\_approval.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_gate_approval.md)

## Description

telegram-prompt-actions: In the sase-telegram repository, replace synchronous resolve_gate_response execution and settlement in inbound handlers with the shared durable submission API. Acknowledge callbacks promptly, remove or disable accepted decision keyboards, persist completion/error delivery and keyboard-cleanup retries, and continue processing later updates while gate execution runs. Reconcile externally accepted gates independently of slow handlers and outbound PDF/message delivery. Test authentication, duplicate callbacks, restart recovery, rate limits, input/feedback flows and cross-surface dismissal without real Telegram sends. Preserve the existing polling entry point for the receiver phase to integrate.

## Notes

[2026-09-14T13:38:17Z · sase-zr.4] PROPOSED FOLLOW-UP: sase (primary repo) src/sase/monitor/store_lane.py:23-24 has dead `from .store import monitor_records as _monitor_records` / `from .store import project_records as _project_records` imports left over from commit d2ba89cb42 (fix(monitor): keep lookup helpers private, sase-zr.2), which privatized both names in store.py (to `_monitor_records`/`_project_records`) but only updated the module-attribute call sites, not these two direct-name imports — importing sase.monitor.store_lane now raises ImportError unconditionally. Discovered via sase-telegram test_custom_gates.py::test_launch_approval_uses_the_same_singleton_renderer, which transitively imports it through sase.gate_shell.transaction; confirmed unrelated to this phase by reproducing on a clean sase-telegram checkout.

[2026-09-14T13:39:02Z · sase-zr.4] PROPOSED FOLLOW-UP: sase-telegram tests/test_inbound.py::TestUpdateCommand.test_update_completion_scan_{sends_success_once,prefers_failure_message,falls_back_to_exit_code} assume pytest tmp_path never falls under $HOME; on a host/sandbox where TMPDIR is nested under $HOME (e.g. this workspace's .cache/sase/tmp/agent-tmp/...), _format_update_completion/_shorten_home shortens the expected log_path to a leading "~/", so the assert_called_once_with comparisons fail even though behavior is correct. Pre-existing, confirmed via git stash on a clean checkout; unrelated to this phase.

[2026-09-14T13:39:55Z · sase-zr.4] Replaced sase-telegram's synchronous execute_gate_selection call (inbound.resolve_gate_response) with a durable submission through the shared supervised-proc API (submit_proc_request + ProcSubmitRequest, argv=['sase','gate','answer','--id',...,'--kind',...,'--no-detach','--json']), mirroring 'sase gate answer --detach' for every gate answered via Telegram (not just shell-backed ones) so slow option commands/archive/launch no longer block the inbound poll loop or delay later updates in the same batch; gate-shell settlement is now the reinvoked CLI's own already-tested responsibility instead of Telegram's. Added a fast synchronous already-answered/cancelled pre-check so stale taps still reject immediately without spawning a proc. Added durable completion/error delivery (inbound.GATE_COMPLETION_PENDING_DIR + sase_tg_inbound._send_ready_gate_completions/_latest_gate_execution_error/_format_gate_*), scanned every inbound tick, reporting success (from response.json), a recorded execution error, or a terminal-but-non-success proc exit as a follow-up message since the original callback popup may have expired. Fixed the keyboard-cleanup durability gap the plan named: _dismiss_gate_callback/_dismiss_resolved_button now route through _dismiss_button_with_retry, which persists a tombstone before attempting the Telegram edit and only clears it on success, retried on later ticks via _retry_pending_keyboard_cleanups (wired into main()) instead of silently losing track of a stale keyboard when the edit fails. Verified: sase-telegram's just lint (ruff+mypy) and just check both run clean except 4 pre-existing, confirmed-unrelated failures (1 sase-core monitor.store_lane ImportError from a prior commit, 3 tmp_path-under-$HOME test fragility in existing /update completion tests) -- both reproduced on a clean checkout via git stash and recorded as PROPOSED FOLLOW-UP notes on this bead. 594 tests pass including 3 rewritten submission-contract tests (test_gate_shell_settlement.py), 1 updated registry test, and 10 new tests covering gate-completion delivery (success/error/proc-failure/still-running/send-failure) and keyboard-cleanup retry durability. sase bead epic-symbols sase-zr.4 reported no entries.

## Dependencies

- **Depends on:** [sase-zr.2](sase-zr.2.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zr.5](sase-zr.5.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.4/README.md) | [sase-zr.4](sase-zr.4.md) | 0 |

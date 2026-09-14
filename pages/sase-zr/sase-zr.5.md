# Bead: sase-zr.5 — Remove Telegram's periodic polling delay

[Bead Pages](../README.md) / [sase-zr](README.md) / sase-zr.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0js` · **Assignee:** `sase-zr.5` · **Size:** medium
**Created:** 2026-09-12 05:06:18 EDT · **Closed:** 2026-09-14 10:27:04 EDT
**Plan:** [202609/prompt\_gate\_approval.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_gate_approval.md)

## Description

telegram-continuous-receiver: Measure the effective inbound cadence and integrate a supervised, single-owner long-poll receiver with sase-telegram's existing chop entry point. Preserve --once, disabled-credential behavior and axe stop/config lifecycle. Keep local cleanup independent of the network poll, durably claim actionable updates before advancing offsets, and preserve ordering for mutable question/input progress and non-gate launches. Test receiver restart, two competing pollers, offset replay, rate limits, idle CPU and prompt cleanup during a long poll. Reuse SASE supervision rather than adding an unsupervised process or new queue service.

## Notes

[2026-09-14T14:25:51Z · sase-zr.5] PROPOSED FOLLOW-UP: sase-telegram tests/test_inbound.py::TestUpdateCommand (3 tests: test_update_completion_scan_sends_success_once, test_update_completion_scan_prefers_failure_message, test_update_completion_scan_falls_back_to_exit_code) fail in this sandboxed agent environment because pytest tmp_path resolves under /home/bryan/.cache/..., which sits under this environments $HOME (/home/bryan) — _shorten_home() then collapses the expected absolute log path to a ~/-relative one, mismatching the hardcoded-absolute-path test assertions. Pre-existing on master (confirmed via git stash before this change); unrelated to sase-zr.5. Needs either a tmp_path fixture outside $HOME or assertions that tolerate the ~ shortening.

[2026-09-14T14:27:04Z · sase-zr.5] Implemented in sase-telegram: added src/sase_telegram/receiver.py (ensure_receiver_running, idempotent submit_proc_request with a chat-id-derived request_fingerprint/concurrency_key so a receiver already active for the configured bot replays instead of spawning a duplicate). Refactored sase_tg_inbound.py's main() into three paths: --once (unchanged poll-once diagnostics/tests path), --receiver (new persistent getUpdates(timeout=30) loop, self-terminates on disabled Telegram/invalid credentials so the next chop tick re-arms it), and the default bare chop tick (now only local cleanup + ensure_receiver_running(), no network poll -- keeps the 5s cleanup cadence independent of the receiver's long poll). Offset now advances per-update (after each update finishes, success or caught/logged error) instead of once per batch, so a killed receiver cannot silently lose an unclaimed update and one poisoned update cannot wedge the rest of the batch. Measured actual chop cadence via ~/.sase/axe/lumberjacks/telegram/status.json (interval=5, ~5.15s/tick actual), confirming the plan's 'five-second chop tick' comment. Verified: just check in sase-telegram (lint clean: ruff+mypy; 607 passed, 3 pre-existing unrelated failures in test_inbound.py::TestUpdateCommand confirmed via git-stash baseline and recorded as a PROPOSED FOLLOW-UP note, not caused by this change). New/changed test coverage: two-competing-pollers and receiver-restart-after-crash against the real durable proc store (tests/test_receiver.py::TestSingleOwnerReplay), receiver self-termination on disabled/credential-loss and long-poll-not-busy-loop timeout assertion, backoff-and-retry after a poll failure (rate-limit style), per-update offset durability past a poisoned update, and bare-tick independence from network polling (tests/test_integration.py). Updated docs/inbound.md and README.md for the new --receiver flag and receiver lifecycle/adoption/stop documentation. No sase-core or primary sase repo changes were needed for this phase (epic-symbols: none for sase-zr.5).

## Dependencies

- **Depends on:** [sase-zr.4](sase-zr.4.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zr.6](sase-zr.6.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-zr.5.md) | [sase-zr.5](sase-zr.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-telegram | [`sase-telegram@829e738`](https://github.com/sase-org/sase-telegram/commit/829e73801ba60f0ac8611c30aa8f0c97a95c5e56) | feat(inbound): replace polling gap with a supervised long-poll receiver | [sase-zr.5](sase-zr.5.md) | 2026-09-14 10:28:38 EDT |

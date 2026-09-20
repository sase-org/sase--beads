# Bead: sase-zr.7.4 — Authenticated Telegram updates and TTY-only pre-rejection

[Bead Pages](../README.md) / [sase-zr.7](sase-zr.7.md) / sase-zr.7.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.07](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.07.md) · **Assignee:** `sase-zr.7.4` · **Size:** small
**Created:** 2026-09-16 14:25:14 EDT · **Closed:** 2026-09-16 15:01:27 EDT
**Plan:** [202609/sase\_zr\_close\_out.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_zr_close_out.md)

## Description

telegram-auth: in sase-telegram, reject every update whose effective chat or callback sender is not the configured chat before any handler runs, hide requires_tty options from gate keyboards and pre-reject them before submission, and tag submissions with source telegram.

## Notes

[2026-09-16T19:01:27Z · sase-zr.7.4] Implemented all three telegram-auth requirements in sase-telegram:
1. Chat/sender authentication: _dispatch_one_update now rejects (with a log line, no reply) any update whose effective chat -- and, for callbacks, sender -- doesn't match SASE_TELEGRAM_BOT_CHAT_ID, before any handler runs. Falls open only when the configured chat id itself can't be resolved (unchanged from prior behavior).
2. TTY pre-rejection: render_gate_keyboard (formatting.py) now hides requires_tty options (sudo approve) from singleton and AND-group keyboards, keeping Deny visible. _start_or_submit_gate_selection now also rejects a requires_tty selection server-side before submission (mirrors cli_answer._reject_detached_tty_options), covering a forged/stale callback token naming a hidden branch directly.
3. Source tagging: submit_gate_response's operation payload now includes "source": "telegram", so sase gate answer's acceptance receipt records source=telegram instead of defaulting to cli.
Tests: extended tests/test_integration.py with foreign-chat rejection cases (text/photo/document/callback) plus a positive same-chat-and-sender callback case; extended tests/test_custom_gates.py's registry keyboard test to assert no Approve button for sudo, and added a dedicated test proving a forged approve-branch callback token is still rejected pre-submission; updated tests/test_gate_shell_settlement.py's operation_payload assertions for the new source field.
Verified: sase-telegram's full suite (636 tests), ruff, and mypy all pass (after reinstalling the stale sase-core-rs wheel to match the >=0.34.37 pin and reinstalling the outer sase package from this workspace's local source). sase bead epic-symbols sase-zr.7.4 reported no entries.

## Dependencies

- **Blocks:** [sase-zr.7.5](sase-zr.7.5.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.7.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.7.4/README.md) | [sase-zr.7.4](sase-zr.7.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-telegram | [`sase-telegram@24900c0`](https://github.com/sase-org/sase-telegram/commit/24900c02de4e76e91f7b35fb8f4a3851e97ed4a8) | fix(telegram): authenticate inbound updates and pre-reject TTY-only gate options | [sase-zr.7.4](sase-zr.7.4.md) | 2026-09-16 15:02:54 EDT |

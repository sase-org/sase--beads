# Bead: sase-p.3 — Phase 3 — Inbound logic (pure functions over gchat list-messages output)

[Bead Pages](../README.md) / [sase-p](README.md) / sase-p.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-25 02:43:17 UTC
**Plan:** [202604/retired\_chat\_plugin.md](https://github.com/sase-org/sase--plans/blob/main/202604/retired_chat_plugin.md)

## Description

Repo: retired chat plugin. Port outbound.py (high-water-mark + lock) and add inbound.py pure logic: process_thread_reply, process_text_completion (two-step feedback), process_dot_command (.list/.listx/.kill/.resume/.xprompts), process_attachment, find_externally_handled, confirmation_text. State paths under ~/.sase/gchat/. tests/test_inbound.py and tests/test_outbound.py cover numeric replies, two-step flows, dot-commands, attachments, externally-handled cleanup, lock, high-water-mark. Exit: just check passes; pure-logic functions fully unit-tested without subprocess. See plans/202604/retired_chat_plugin_integration.md Phase 3.

## Dependencies

- **Depends on:** [sase-p.2](sase-p.2.md) ✓
- **Blocks:** [sase-p.4](sase-p.4.md) ✓

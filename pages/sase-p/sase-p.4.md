# Bead: sase-p.4 — Phase 4 — Entry-point scripts + integration tests + docs + final README

[Bead Pages](../README.md) / [sase-p](README.md) / sase-p.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-25 02:43:24 UTC
**Plan:** [202604/retired\_chat\_plugin.md](https://github.com/sase-org/sase--plans/blob/main/202604/retired_chat_plugin.md)

## Description

Repo: retired chat plugin. Implement sase_gc_outbound.py and sase_gc_inbound.py entry-point scripts (lock+is_idle gate, send/upload, persist pending actions, advance high-water mark; offset polling, dispatch to thread reply/text completion/dot-command/attachment/launch-agent, edit message to strike options, post confirmation; --once and --dry-run flags). scripts/__init__.py re-exports. tests/test_integration.py with the gchat CLI patched (plan-approval round trip, HITL feedback two-step, agent-launch from text, photo upload → agent prompt, dot-command .list). docs/architecture.md, docs/outbound.md, docs/inbound.md and final README.md. Exit: just check passes; integration tests green. See plans/202604/retired_chat_plugin_integration.md Phase 4.

## Dependencies

- **Depends on:** [sase-p.3](sase-p.3.md) ✓

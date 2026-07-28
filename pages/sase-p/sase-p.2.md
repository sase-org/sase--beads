# Bead: sase-p.2 — Phase 2 — Outbound formatting (notification → Google Chat markdown + numbered options)

[Bead Pages](../README.md) / [sase-p](README.md) / sase-p.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-25 02:43:10 UTC
**Plan:** [202604/retired\_chat\_plugin.md](https://github.com/sase-org/sase--plans/blob/main/202604/retired_chat_plugin.md)

## Description

Repo: retired chat plugin. Implement formatting.py with format_notification(n) -> (text, options, attachments), per-notification-type formatters (PlanApproval, HITL, UserQuestion, WorkflowComplete, AgentLaunched, AgentKilled, ErrorDigest, ImageGenerated, generic fallback), markdown helpers, _render_options_block, and _truncate_to_pdf cascade adapted for Chat. tests/test_formatting.py pins option-list ordering so inbound can rely on it. Exit: just check passes. See plans/202604/retired_chat_plugin_integration.md Phase 2.

## Dependencies

- **Depends on:** [sase-p.1](sase-p.1.md) ✓
- **Blocks:** [sase-p.3](sase-p.3.md) ✓

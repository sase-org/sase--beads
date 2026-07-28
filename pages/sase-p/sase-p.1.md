# Bead: sase-p.1 — Phase 1 — Repo scaffolding + gchat CLI client + reusable infrastructure

[Bead Pages](../README.md) / [sase-p](README.md) / sase-p.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-25 02:43:04 UTC
**Plan:** [202604/retired\_chat\_plugin.md](https://github.com/sase-org/sase--plans/blob/main/202604/retired_chat_plugin.md)

## Description

Repo: retired chat plugin. Stand up pyproject.toml/Justfile/CLAUDE.md/AGENTS.md/sase.yml, credentials.py (env-var helpers — no pass), gchat_client.py (subprocess wrapper around the gchat CLI: send/edit/upload/download/list/react with retry+debug log), option_codes.py (out-of-band action encoder, smaller than callback_data.py), and port pending_actions.py/rate_limit.py/pdf_convert.py/pdf_style.css from sase-telegram with paths rewritten to ~/.sase/gchat/. Tests for credentials/gchat_client (subprocess mocked)/option_codes/pending_actions/rate_limit. Exit: just install && just check passes. See plans/202604/retired_chat_plugin_integration.md Phase 1.

## Dependencies

- **Blocks:** [sase-p.2](sase-p.2.md) ✓

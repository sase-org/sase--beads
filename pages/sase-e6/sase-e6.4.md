# Bead: sase-e6.4 — Chat markdown stores both prompt renderings

[Bead Pages](../README.md) / [sase-e6](README.md) / sase-e6.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rs](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rs/README.md) · **Assignee:** `sase-e6.4` · **Size:** medium
**Created:** 2026-08-02 13:22:48 UTC
**Plan:** [202608/stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/stored_prompt_duality.md)

## Description

chat: extend the chat writer with sentinel-delimited XPrompt and rendered-prompt sections, harden turn parsing against them, update every `save_chat_history` caller to supply both renderings, and linkify references in the stored XPrompt section.

## Dependencies

- **Depends on:** [sase-e6.3](sase-e6.3.md) ◐
- **Blocks:** [sase-e6.6](sase-e6.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e6.4/README.md) | [sase-e6.4](sase-e6.4.md) | 0 |

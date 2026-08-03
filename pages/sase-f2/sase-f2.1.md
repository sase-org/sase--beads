# Bead: sase-f2.1 — Chat markdown returns to a single Prompt section

[Bead Pages](../README.md) / [sase-f2](README.md) / sase-f2.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ej.land.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.land.w2/README.md) · **Assignee:** `sase-f2.1` · **Size:** medium
**Created:** 2026-08-03 14:48:24 EDT
**Plan:** [202608/revert\_stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_stored_prompt_duality.md)

## Description

chat: strip the sentinel-delimited XPrompt and rendered-prompt sections out of the chat writer, drop the two keyword arguments from every `save_chat_history` caller, remove the parser's strip pass, and delete the `chat_history.rendered_prompt_max_bytes` config field.

## Dependencies

- **Blocks:** [sase-f2.3](sase-f2.3.md) ◐
- **Blocks:** [sase-f2.4](sase-f2.4.md) ◐
- **Blocks:** [sase-f2.6](sase-f2.6.md) ◐

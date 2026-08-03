# Bead: sase-f2.1 — Chat markdown returns to a single Prompt section

[Bead Pages](../README.md) / [sase-f2](README.md) / sase-f2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ej.land.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.land.w2/README.md) · **Assignee:** `sase-f2.1` · **Size:** medium
**Created:** 2026-08-03 14:48:24 EDT · **Closed:** 2026-08-03 15:27:55 EDT
**Plan:** [202608/revert\_stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_stored_prompt_duality.md)

## Description

chat: strip the sentinel-delimited XPrompt and rendered-prompt sections out of the chat writer, drop the two keyword arguments from every `save_chat_history` caller, remove the parser's strip pass, and delete the `chat_history.rendered_prompt_max_bytes` config field.

## Notes

[2026-08-03T19:27:55Z · sase-f2.1] Verified chat writer no longer emits sentinel prompt sections or accepts xprompt/rendered prompt kwargs; focused chat/finalization/postprocessing tests passed; focused Agent CLI visual regression passed after restoring fixture default; just check passed.

## Dependencies

- **Blocks:** [sase-f2.3](sase-f2.3.md) ✓
- **Blocks:** [sase-f2.4](sase-f2.4.md) ✓
- **Blocks:** [sase-f2.6](sase-f2.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-f2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-f2.1/README.md) | [sase-f2.1](sase-f2.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`376a3b1`](https://github.com/sase-org/sase/commit/376a3b1bbcb0dad5cccab0650611c7898aa49f3a) | feat(history)!: restore single-prompt chat markdown | [sase-f2.1](sase-f2.1.md) | 2026-08-03 15:30:11 EDT |

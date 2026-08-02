# Bead: sase-e6.4 — Chat markdown stores both prompt renderings

[Bead Pages](../README.md) / [sase-e6](README.md) / sase-e6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rs](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rs/README.md) · **Assignee:** `sase-e6.4` · **Size:** medium
**Created:** 2026-08-02 13:22:48 UTC · **Closed:** 2026-08-02 16:05:02 UTC
**Plan:** [202608/stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/stored_prompt_duality.md)

## Description

chat: extend the chat writer with sentinel-delimited XPrompt and rendered-prompt sections, harden turn parsing against them, update every `save_chat_history` caller to supply both renderings, and linkify references in the stored XPrompt section.

## Notes

[2026-08-02T16:05:02Z · sase-e6.4] Implemented sentinel-delimited Agent XPrompt and rendered-prompt chat sections with hosted xprompt links, UTF-8 byte-capped/fence-safe rendering, parser stripping, and caller plumbing; verified focused chat/finalizer/config/link tests, the isolated bead-contention regression after a host-contention flake, and a clean full just check (25k+ tests).

[2026-08-02T16:06:21Z · sase-e6.4] Implemented sentinel-delimited Agent XPrompt and rendered-prompt chat sections with hosted xprompt links, UTF-8 byte-capped/fence-safe rendering, parser stripping, and caller plumbing; verified focused chat/finalizer/config/link tests, the isolated bead-contention regression after a host-contention flake, and a clean full just check (25k+ tests).

## Dependencies

- **Depends on:** [sase-e6.3](sase-e6.3.md) ✓
- **Blocks:** [sase-e6.6](sase-e6.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e6.4/README.md) | [sase-e6.4](sase-e6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`e6624e3`](https://github.com/sase-org/sase/commit/e6624e324e7857a1967757c8b22984ff7d49b4a8) | feat(history): store both prompt renderings in chats | [sase-e6.4](sase-e6.4.md) | 2026-08-02 16:09:29 |

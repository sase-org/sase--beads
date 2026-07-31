# Bead: sase-ci.2 — Registry-driven gate rendering and resolution in sase-telegram

[Bead Pages](../README.md) / [sase-ci](README.md) / sase-ci.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qh/README.md) · **Assignee:** `sase-ci.2` · **Size:** medium
**Created:** 2026-07-31 16:13:20 UTC · **Closed:** 2026-07-31 16:37:19 UTC
**Plan:** [202607/telegram\_generic\_gate\_support.md](https://github.com/sase-org/sase--plans/blob/main/202607/telegram_generic_gate_support.md)

## Description

telegram-gates: replace the six hardcoded action/kind allowlists in the sase-telegram plugin with registry lookups and rename the custom-gate formatter into an adapter-driven generic gate formatter, so TaskTriage and every future kind render with buttons, attachments, and a working callback path.

## Notes

[2026-07-31T16:37:19Z · sase-ci.2] Implemented registry-driven Telegram gate rendering and resolution in the linked sase-telegram repo: removed the six duplicated action/kind allowlists, added adapter-driven generic formatting with inline previews and registered-action icon fallback, enabled TaskTriage pending tracking and callback execution (including required Close feedback), and updated inbound/outbound docs. Verified with focused tests (17 passed) and just check (Ruff clean, mypy clean, 505 tests passed).

[2026-07-31T16:38:23Z · sase-ci.2] Finalizer verification: focused gate tests passed (17), and just check passed with Ruff, mypy, and all 505 tests.

## Dependencies

- **Depends on:** [sase-ci.1](sase-ci.1.md) ✓
- **Blocks:** [sase-ci.3](sase-ci.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ci.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ci.2/README.md) | [sase-ci.2](sase-ci.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-telegram | [`sase-telegram@c3e6d16`](https://github.com/sase-org/sase-telegram/commit/c3e6d16ab342de959478f2e894ad105b56ba688e) | feat: drive Telegram gates from adapter registry | [sase-ci.2](sase-ci.2.md) | 2026-07-31 16:38:49 |

# Bead: sase-x.6 — Phase 6: Cross-Integration Consistency Pass

[Bead Pages](../README.md) / [sase-x](README.md) / sase-x.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-x.6`
**Created:** 2026-04-27 16:45:41 UTC
**Plan:** [202604/gchat\_telegram\_integration\_improvements.md](https://github.com/sase-org/sase--plans/blob/main/202604/gchat_telegram_integration_improvements.md)

## Description

Land the work as a coherent sibling integration improvement rather than a set of unrelated patches.

## Notes

Phase 6 final summary — sibling-integration consistency pass.

User-visible changes (across plugin repos):
- retired chat plugin README.md and docs/inbound.md: dot-commands tables updated
  to include the .help, .retry/.r, and the no-arg .kill picker landed
  in phases sase-x.1 / sase-x.2.
- sase-telegram README.md and docs/inbound.md: corrected to describe
  agent management as slash commands (/list, /listx, /kill, /resume,
  /xprompts) — the docs had a stale "dot-commands" reference even
  though the inbound script always dispatched on / -prefixed commands
  and registers them with set_my_commands.

Notable technical changes: none — code/tests in both plugin repos were
already consistent and correct after phases 1-5. The drift was purely
in user-facing docs.

Verification:
- retired chat plugin: just check → 265 passed.
- sase-telegram: just check → 219 passed (after re-running `just install`
  to refresh stale .venv state — sase entry-points for sase_llm
  providers were missing from the previously-installed metadata).
- No changes to sase_100 were required.

Commands compared (by design after phases 1-5):
| Command set     | gchat (dot-commands) | telegram (slash commands)              |
| --------------- | -------------------- | -------------------------------------- |
| List running    | .list                | /list                                  |
| List done       | .listx               | /listx                                 |
| Kill picker     | .kill                | /kill (inline keyboard)                |
| Kill named      | .kill <name> ...     | /kill <name>                           |
| Resume targets  | .resume              | /resume (inline copy buttons)          |
| Retry           | .retry <name> / .r   | 🔄 Retry callback button on launch /kill |
| xprompts catalog| .xprompts            | /xprompts                              |
| Help            | .help                | (Telegram's set_my_commands UI)        |

Intentional divergence preserved per the plan: "Google Chat should lean
on threads and dot commands; Telegram should keep button-heavy
workflows." The Telegram retry path is button-driven; the gchat retry
path is typed.

Deferred follow-ups documented in retired chat plugin/ROADMAP.md:
- Reactions on plan approvals (gchat-only UX)
- Streaming / draft API limitations (Google Chat platform constraints)
- .retry polish — no-arg .retry list, recovered-prompt preview
- Dot-command argument hints (e.g. --filter <substring>)

No equivalent ROADMAP exists in sase-telegram and none was added in
this phase — the gaps relative to gchat are deliberate platform-specific
divergences, not parity debt.

## Dependencies

- **Depends on:** [sase-x.1](sase-x.1.md) ✓
- **Depends on:** [sase-x.2](sase-x.2.md) ✓
- **Depends on:** [sase-x.3](sase-x.3.md) ✓
- **Depends on:** [sase-x.4](sase-x.4.md) ✓
- **Depends on:** [sase-x.5](sase-x.5.md) ✓

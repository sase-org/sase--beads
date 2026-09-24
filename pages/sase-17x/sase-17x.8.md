# Bead: sase-17x.8 — Transcript block interactions and lifecycle

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.8` · **Size:** medium
**Created:** 2026-09-24 11:29:27 EDT · **Closed:** 2026-09-24 15:30:43 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

transcript-blocks: add NORMAL-mode block navigation with expand, pager, kill, rerun, edit, copy, open-in-Procs and remove. Add completion toasts while hidden, unseen dots, restore after a TUI restart, pruned-record handling, and `⏎` from a Procs command-line row back to its block.

## Notes

[2026-09-24T19:30:06Z · sase-17x.8] PROPOSED FOLLOW-UP: just check blocked by 10 pre-existing mypy errors in ace/tui/widgets/_agent_detail_display.py and _agent_detail_state.py (untouched by this phase; fallout from legacy agents UI removal)

[2026-09-24T19:30:23Z · sase-17x.8] PROPOSED FOLLOW-UP: make transcript block-nav keys configurable under ace.keymaps.command_line (Keys table claims configurable; this phase used fixed screen BINDINGS following the ProcsPane pattern)

[2026-09-24T19:30:43Z · sase-17x.8] transcript-blocks done: NORMAL-mode nav (j/k/g/G/o/enter/v/K/r/R/e/y/Y/p/x/i/a) with input forwarding; hidden-finish toasts with live key hint; unseen dots cleared on view; 24h/20-row restore below earlier divider with lazy tails and exit watches; pruned blocks keep cached tail; rotation marker; Procs Enter jumps to block via proc_focus_target (monitor rows keep agent jump). Verified: 60 command_line + 90 procs-pane tests pass; mypy/ruff/fmt clean on touched files; 3 new + 4 updated PNG goldens current. just check still red only on 10 pre-existing mypy errors in untouched _agent_detail files (filed as follow-up).

## Dependencies

- **Blocks:** [sase-17x.11](sase-17x.11.md) ◐ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.7](sase-17x.7.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.8/README.md) | [sase-17x.8](sase-17x.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`98c8312`](https://github.com/sase-org/sase/commit/98c8312f96f6b8f50303f7d6b6106c31a6afd03b) | feat(ace): command-line transcript blocks with NORMAL-mode navigation | [sase-17x.8](sase-17x.8.md) | 2026-09-24 15:38:28 EDT |

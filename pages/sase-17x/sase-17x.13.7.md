# Bead: sase-17x.13.7 — Foreground interpreter, writes chips, and UI-thread I/O

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.7` · **Size:** medium
**Created:** 2026-09-24 20:28:48 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

policy-io: run foreground commands with the TUI's interpreter and fix the missing writes classifications. Move history, the tip marker, kill, the Procs jump store read and tail reads off the UI thread. Keep history in session-held memory that updates on exit.

## Dependencies

- **Depends on:** [sase-17x.13.4](sase-17x.13.4.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.13.8](sase-17x.13.8.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.7/README.md) | [sase-17x.13.7](sase-17x.13.7.md) | 0 |

# Bead: sase-1co.4 — TUI prompt input editing for mid-word alternation

[Bead Pages](../README.md) / [sase-1co](README.md) / sase-1co.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u1.md) · **Assignee:** `sase-1co.4` · **Size:** medium
**Created:** 2026-09-29 16:22:06 EDT
**Plan:** [202609/midword\_alternation.md](https://github.com/sase-org/sase--plans/blob/main/202609/midword_alternation.md)

## Description

tui-alt-editing: in sase, make brace padding and `|` separator normalization recognize mid-word openers. Ignore openers in literal zones, keep an unclosed span to its own line, and let the innermost nested span win. Stop Jinja auto-pairing right after `%{`, then update tests and `docs/ace.md`.

## Dependencies

- **Depends on:** [sase-1co.3](sase-1co.3.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1co.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.4/README.md) | [sase-1co.4](sase-1co.4.md) | 0 |

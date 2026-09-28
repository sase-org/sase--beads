# Bead: sase-1ca.1 — Seal pytest home isolation and remove the stash-popping test bug

[Bead Pages](../README.md) / [sase-1ca](README.md) / sase-1ca.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tt.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tt.w0.md) · **Assignee:** `sase-1ca.1` · **Size:** medium
**Created:** 2026-09-28 17:30:09 EDT
**Plan:** [202609/never\_lose\_stashed\_prompts.md](https://github.com/sase-org/sase--plans/blob/main/202609/never_lose_stashed_prompts.md)

## Description

seal-pytest-home: fix the monkeypatch.undo() test that popped the real stash, remove every undo() on the shared monkeypatch fixture, add an undo-proof session-level HOME/SASE_HOME sandbox, an AST guard test, a seal regression test, and SASE_HOME forwarding for tmux-launched TUIs.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ca.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ca.1.md) | [sase-1ca.1](sase-1ca.1.md) | 0 |

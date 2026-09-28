# Bead: sase-1ca.1 — Seal pytest home isolation and remove the stash-popping test bug

[Bead Pages](../README.md) / [sase-1ca](README.md) / sase-1ca.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tt.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tt.w0.md) · **Assignee:** `sase-1ca.1` · **Size:** medium
**Created:** 2026-09-28 17:30:09 EDT · **Closed:** 2026-09-28 17:55:23 EDT
**Plan:** [202609/never\_lose\_stashed\_prompts.md](https://github.com/sase-org/sase--plans/blob/main/202609/never_lose_stashed_prompts.md)

## Description

seal-pytest-home: fix the monkeypatch.undo() test that popped the real stash, remove every undo() on the shared monkeypatch fixture, add an undo-proof session-level HOME/SASE_HOME sandbox, an AST guard test, a seal regression test, and SASE_HOME forwarding for tmux-launched TUIs.

## Notes

[2026-09-28T21:54:56Z · sase-1ca.1--1] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on rule 7 — closed flag bead sase-1be still has surviving agent_tabs definition; reproduces identically on clean base tree (verified via stash), unrelated to this phase

[2026-09-28T21:55:23Z · sase-1ca.1--1] Phase complete: removed all monkeypatch.undo() on shared fixture (stash-restore test now uses scoped context + asserts tmp rows a,b and tmp path; notification/settlement tests scoped; tz_divergence owns private MonkeyPatch); added session-scoped _sandbox_session_home baseline; added AST guard + seal regression tests (tests/test_pytest_isolation_guards.py); _tmux_env_args forwards SASE_HOME with unit tests. Verified: 64 passed (guards/tmux/notification/settlement), 17 passed (stash-restore), 50 passed (focus-steal/vim-containment); real ~/.sase/logs/tui_startup.jsonl untouched since 17:53. just check fails only on pre-existing rule-7 flag lint (sase-1be agent_tabs), reproduced on clean base tree.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ca.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ca.1.md) | [sase-1ca.1](sase-1ca.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`703b042`](https://github.com/sase-org/sase/commit/703b042c236d915bcc44635e702267cad36361be) | feat(ace): add tmux launch, isolation guards, notification settlement and stash-restore coverage | [sase-1ca.1](sase-1ca.1.md) | 2026-09-28 18:18:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ca.1--1][1] | Need phase scope and design | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ca.1.md

<!-- sase:referenced-by:end -->

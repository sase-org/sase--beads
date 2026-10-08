# Bead: sase-1i4.2 — Agent runner sweeps its own scope

[Bead Pages](../README.md) / [sase-1i4](README.md) / sase-1i4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5s](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5s.md) · **Assignee:** `sase-1i4.2` · **Size:** medium
**Created:** 2026-10-08 06:37:34 EDT · **Closed:** 2026-10-08 07:59:20 EDT
**Plan:** [202610/agent\_scope\_leak\_reaping.md](https://github.com/sase-org/sase--plans/blob/main/202610/agent_scope_leak_reaping.md)

## Description

runner-teardown: add the shared scope-sweep module, the agent_scope_teardown config block, and the runner hooks that kill non-descendant, non-spared processes in the runner's own sase-agent scope before shutdown finalization and between in-process successor turns.

## Notes

[2026-10-08T11:42:31Z · sase-1i4.2--1] PROPOSED FOLLOW-UP: just check symvision gate is red on the clean base tree too (verified byte-identical unused-public list via git stash; see sase-1hp which tracks the accumulated unused-public backlog)

[2026-10-08T11:59:03Z · sase-1i4.2--2] PROPOSED FOLLOW-UP: symvision NEW BeadStoreFingerprint in src/sase/core/bead_read_facade.py reproduces on fully clean base tree (verified via git stash -u + native just _lint-symvision; both BeadBoardSnapshot and BeadStoreFingerprint present without this phase touching that file); triage labels it NEW only from zero witnesses, tracked by backlog bead sase-1hp

[2026-10-08T11:59:20Z · sase-1i4.2--2] runner-teardown done: scope_sweep module + teardown config + runner exit/turn hooks landed. Verified: tests/test_agent_scope_sweep.py 21 passed; detach_scope suites pass (38 with sweep file); just check green except pre-existing symvision base drift (BeadStoreFingerprint/BeadBoardSnapshot reproduce byte-identical on clean base, tracked by sase-1hp, triage NEW label is witness lag on untouched file). epic-symbols empty.

## Dependencies

- **Depends on:** [sase-1i4.1](sase-1i4.1.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1i4.3](sase-1i4.3.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1i4.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1i4.2.md) | [sase-1i4.2](sase-1i4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e4b0faf`](https://github.com/sase-org/sase/commit/e4b0faf443accef65ebc2a78612f4f92dc9c3151) | feat(scope): runner sweeps its own agent scope on exit and turn boundaries | [sase-1i4.2](sase-1i4.2.md) | 2026-10-08 08:01:18 EDT |

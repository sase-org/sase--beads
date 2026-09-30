# Bead: sase-1cx.4 — Ceiling-bounded wait, follow, and the escalation block

[Bead Pages](../README.md) / [sase-1cx](README.md) / sase-1cx.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u3.md) · **Assignee:** `sase-1cx.4` · **Size:** medium
**Created:** 2026-09-29 20:32:18 EDT · **Closed:** 2026-09-30 12:17:29 EDT
**Plan:** [202609/tool\_run\_escalation.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_run_escalation.md)

## Description

bounded-wait: extract a shared `follow_run` helper from `show -F` without changing its output. Bound agent `sase tool wait` and `show -F` by the core-computed sync wait budget, and print one shared escalation block (the `-J/--join` form) when a joinable run is still going.

## Notes

[2026-09-30T16:16:51Z · sase-1cx.4] PROPOSED FOLLOW-UP: symvision still flags 5 pre-existing symbols (HandoffSubmitResult, StarterResolution, owner_ref, tool_run_join, tool_run_release_join); verified identical on clean HEAD worktree, so just _lint-symvision stays red on base — needs epic-symbol entries or a land-agent decision

[2026-09-30T16:17:29Z · sase-1cx.4] bounded-wait landed: follow_run helper extracted (show -F byte-identical unbounded), sync_wait_budget adapter + shared escalation block in routing.py, wait/show -F bounded with exit 124 and JSON escalation object. Verified: 12 new tests/tool/test_bounded_wait.py pass; full tests/tool 375 passed/1 skipped; lifecycle/query/routing + completion snapshot 56 passed; detach 19 passed; ruff/mypy/test-waits clean; symvision adds no new flags (5 leftovers reproduce identically on HEAD worktree, filed as PROPOSED FOLLOW-UP). cli_spec.json regenerated (also picks up pre-existing bead-attach drift). Docs: ceiling-bounded wait in docs/tool.md, wait/show -F help documents 124.

## Dependencies

- **Depends on:** [sase-1cx.2](sase-1cx.2.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cx.3](sase-1cx.3.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.5](sase-1cx.5.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.6](sase-1cx.6.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cx.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cx.4/README.md) | [sase-1cx.4](sase-1cx.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ba63b3d`](https://github.com/sase-org/sase/commit/ba63b3d37cd861218346819fee99ded36a73af7c) | feat(tool): add bounded wait with escalation budget for show and wait | [sase-1cx.4](sase-1cx.4.md) | 2026-09-30 12:20:49 EDT |

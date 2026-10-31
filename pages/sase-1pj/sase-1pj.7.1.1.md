# Bead: sase-1pj.7.1.1 — Shared retention policy and guarded claim settlement

[Bead Pages](../README.md) / [sase-1pj.7.1](sase-1pj.7.1.md) / sase-1pj.7.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.7.md) · **Assignee:** `sase-1pj.7.1.1` · **Size:** medium
**Created:** 2026-10-31 08:52:40 EDT · **Closed:** 2026-10-31 10:53:25 EDT
**Plan:** [202610/carried\_workspace\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202610/carried_workspace_retention.md)

## Description

retention-core: add the Rust retention decision and Python evidence/effect adapter, preserving exact claim ownership and snapshotting held work.

## Notes

[2026-10-31T14:53:25Z · sase-1pj.7.1.1] Verified shared retention-core: Rust decide_workspace_retention truth table (same/different successor, historical carried_to, stale owner, missing baseline, probe fail, proven clean, foreign dirt, creator restored, gate-released); pin/checked-release identity matching under ProjectSpec lock; PyO3 round-trips; Python adapter persist-then-pin with temp repos and real RUNNING claims (primary-clean/linked-dirty, staged/untracked, repeated hold, claim-transfer race); hold expected_pid and release artifacts_timestamp no-ops; worktree_recovery wrap keeps diagnostics/worktree_recovery.diff. sase-core sase tool run check green; sase sase tool run check green (scoped tests 37m). epic-symbols empty for this phase (adapter API keyed to sase-1pj.7.1.2).

## Dependencies

- **Blocks:** [sase-1pj.7.1.2](sase-1pj.7.1.2.md) ◐ · ⧖ 2026-10-31
- **Blocks:** [sase-1pj.7.1.3](sase-1pj.7.1.3.md) ◐ · ⧖ 2026-10-31

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.7.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.7.1.1/README.md) | [sase-1pj.7.1.1](sase-1pj.7.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@80338d6`](https://github.com/sase-org/sase-core/commit/80338d6bc0a621b1e878fc42865f304f21d6c0c1) | feat(workspace\_retention): classify stranded handoff claim settlement | [sase-1pj.7.1.1](sase-1pj.7.1.1.md) | 2026-10-31 10:54:36 EDT |

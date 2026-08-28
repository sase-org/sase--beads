# Bead: sase-vd.1 — VCS setup adopts the runner's existing workspace

[Bead Pages](../README.md) / [sase-vd](README.md) / sase-vd.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ft](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ft.md) · **Assignee:** `sase-vd.1` · **Size:** medium
**Created:** 2026-08-28 18:06:18 EDT · **Closed:** 2026-08-28 18:43:25 EDT
**Plan:** [202608/one\_workspace\_per\_agent\_family.md](https://github.com/sase-org/sase--plans/blob/main/202608/one_workspace_per_agent_family.md)

## Description

adopt-runner-workspace: make the `#git:` and `#gh:` setup steps adopt the live numbered RUNNING claim already held by the calling runner instead of allocating a second workspace, treating adoption exactly like the existing launcher pre-allocation branch (no second claim, no duplicate occupant record, `should_release=false`), while leaving explicit `n=<num>` pinning and genuinely workspace-less callers on their current allocate path.

## Notes

[2026-08-28T22:42:55Z · sase-vd.1] PROPOSED FOLLOW-UP: #git: setup still claims with os.getpid() and has no occupancy/occupant-record path — unlike #gh: setup, so an allocate-path RUNNING row dies with the setup subprocess and prepare/checkout is unguarded.

[2026-08-28T22:43:25Z · sase-vd.1] Verified #git:/#gh: setup adopts the runner parent pid numbered pool claim (UNIFIED_MIN_WORKSPACE+) with should_release=false, no second claim, no occupant rewrite; skipped adoption for #0, reserved 1-9, explicit n=, and SASE_*_PRE_ALLOCATED; occupancy refusal on an adopted gh checkout releases nothing. just check passed (lint + 1485 scoped test files). sase-github tests/test_gh_workspace_claims.py: 27 passed. epic-symbols sase-vd.1: none leftover.

## Dependencies

- **Blocks:** [sase-vd.3](sase-vd.3.md) ◐ · ⧖ 2026-08-28
- **Blocks:** [sase-vd.5](sase-vd.5.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vd.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.1/README.md) | [sase-vd.1](sase-vd.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8426315`](https://github.com/sase-org/sase/commit/84263159f6499bf922e33ae58c7b4ce193e6698f) | feat(git-setup): adopt the runner's numbered workspace claim | [sase-vd.1](sase-vd.1.md) | 2026-08-28 18:44:44 EDT |

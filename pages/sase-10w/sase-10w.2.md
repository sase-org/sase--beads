# Bead: sase-10w.2 — Test-owned git identity for every test-created repository

[Bead Pages](../README.md) / [sase-10w](README.md) / sase-10w.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0kh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0kh.md) · **Assignee:** `sase-10w.2` · **Size:** medium
**Created:** 2026-09-14 09:06:46 EDT · **Closed:** 2026-09-14 10:05:29 EDT
**Plan:** [202609/green\_ci\_fast\_lane\_v0\_17\_2.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_ci_fast_lane_v0_17_2.md)

## Description

hermetic-git-identity: export a fixture-owned git config and author/committer identity for the whole suite plus a redirected-HOME guard test, so the CI 'Author identity unknown' class can never silently return.

## Notes

[2026-09-14T14:05:29Z · sase-10w.2] Implemented suite-wide fixture-owned git identity with redirected-HOME guard; verified tests/sdd/test_git_identity_fixture.py, redirected-HOME tests/sdd, tests/sdd_store, representative core/Justfile checks, and just check (full-suite escalation) all pass; epic-symbols returned no entries.

## Dependencies

- **Blocks:** [sase-10w.5](sase-10w.5.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-10w.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-10w.2/README.md) | [sase-10w.2](sase-10w.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cc91c0a`](https://github.com/sase-org/sase/commit/cc91c0aa435c225402a4598dc6adf998ef257510) | test: make git identity hermetic in tests | [sase-10w.2](sase-10w.2.md) | 2026-09-14 11:18:09 EDT |

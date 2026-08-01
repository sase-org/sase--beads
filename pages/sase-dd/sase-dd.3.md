# Bead: sase-dd.3 — Bead filter query and inline filter bar

[Bead Pages](../README.md) / [sase-dd](README.md) / sase-dd.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.r7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.r7/README.md) · **Assignee:** `sase-dd.3` · **Size:** small
**Created:** 2026-08-01 13:53:35 UTC · **Closed:** 2026-08-01 16:44:58 UTC
**Plan:** [202608/artifacts\_beads\_and\_files\_subtabs.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_beads_and_files_subtabs.md)

## Description

beads_filters: parse a bead filter query covering type, status, tier, size, project, people, has, and date terms, prefold it into a reusable record index, and drive an inline completion bar whose hide-closed default stays visible in the info line.

## Notes

[2026-08-01T16:42:22Z · sase-dd.3] PROPOSED FOLLOW-UP: Fix local sase-core plan-header wire schema drift — just check validation fails with Python expecting schema version 3 while installed sase_core_rs reports version 2.

[2026-08-01T16:44:58Z · sase-dd.3] Implemented Beads query parsing, prefolded snapshot index, inline filter bar/session, visible -status:closed default, matched/total counts, and tests. Verified just install; focused Beads suite passed (19 tests); broader Artifacts filter/navigation suite passed (68 tests); just check passes fmt/ruff/mypy/symvision/toobig but is blocked in SASE validation by existing plan-header wire schema drift: expected 3, got 2.

[2026-08-01T16:46:45Z · sase-dd.3] Finalizer rechecked: targeted Beads filtering/navigation tests passed; just check reached the known plan-header schema drift validation blocker.

## Dependencies

- **Depends on:** [sase-dd.2](sase-dd.2.md) ✓
- **Blocks:** [sase-dd.6](sase-dd.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dd.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dd.3/README.md) | [sase-dd.3](sase-dd.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`c194459`](https://github.com/sase-org/sase/commit/c1944592a025e618ab4a6168815c3c7ea73ff052) | feat(artifacts): add Beads pane filtering | [sase-dd.3](sase-dd.3.md) | 2026-08-01 16:49:09 |

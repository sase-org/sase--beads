# Bead: sase-a3.4 — Land the three verbs as one documented contract

[Bead Pages](../README.md) / [sase-a3](README.md) / sase-a3.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a3.4` · **Size:** small
**Created:** 2026-07-27 17:45:54 UTC · **Closed:** 2026-07-27 19:54:29 UTC
**Plan:** [202607/bead\_dep\_subcommands.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_dep_subcommands.md)

## Description

land: reconcile the docs, the generated skill, and `bead onboard` around the finished verb, bump the published core version window, and produce acceptance evidence against the live store.

## Notes

[2026-07-27T19:54:16Z · sase-a3.4] Landed docs/beads.md, bead onboard quick start, and src/sase/xprompts/skills/sase_beads.md for the full dep verb; regenerated provider skills with sase skill init --force and verified init skills --check clean. Bumped sase-core-rs to >=0.12.1,<0.13.0 with uv.lock refreshed; PyPI published minimum check, local core version check, and binding scan passed. Live acceptance: dep list sase-a1.6 --format full rc=0 showed 2 satisfied edges with provenance and Blocked by 0 of 2; dep tree sase-a1 --direction in rc=0 rendered the root-only incoming tree (1 bead, depth 1, 0 active blockers); bare dep rc=0 printed the delegation notice and 16 deps across 11 beads; dep list --format json parsed with count=16; live beads carrying at least one edge=1339 versus the 2026-07-25 research count 1271. Scratch acceptance: three-bead store with two edges, dep rm removed the open blocker, history recorded one dependencies change, and removed-edge count stayed 0 before and after SQLite mirror rebuild. Verification: focused dep/version tests passed (40 tests), isolated suite-gate rerun passed after a transient full-suite gate failure, and SASE_PYTEST_WORKERS=4 just check passed.

## Dependencies

- **Depends on:** [sase-a3.2](sase-a3.2.md) ✓
- **Depends on:** [sase-a3.3](sase-a3.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a3.4/README.md) | [sase-a3.4](sase-a3.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`830245c`](https://github.com/sase-org/sase/commit/830245c8cdf01ef0f60c3b86346fba02a0b6d68a) | fix(bead): require core dependency removal support (sase-a3.4) | [sase-a3.4](sase-a3.4.md) | 2026-07-27 19:56:57 |

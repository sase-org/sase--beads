# Bead: sase-b1.2 — Thread provenance to the spawn point

[Bead Pages](../README.md) / [sase-b1](README.md) / sase-b1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b1.2` · **Size:** medium
**Created:** 2026-07-30 01:09:48 UTC · **Closed:** 2026-07-30 01:56:13 UTC
**Plan:** [202607/xprompt\_swarm\_stats.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_swarm_stats.md)

## Description

launch-env-plumbing: thread the per-segment swarm chain through the CLI and ACE launch paths alongside segment_template_groups, inject it into each spawned slot's environment like SASE_MULTI_AGENT_PROMPT_FILE, cover the single-segment fall-throughs, and scrub it from nested launches.

## Notes

[2026-07-30T01:56:13Z · sase-b1.2] Implemented per-segment xprompt-swarm provenance through CLI and ACE multi/single/fan-out/repeat launch paths, JSON-encoded it into SASE_LAUNCH_SWARM_XPROMPTS for each spawned slot, and scrubbed ambient provenance from nested launches. Verified 59 focused launch/env/TUI tests pass; just lint passes Ruff, mypy, Symvision, and structural checks; full just test reached 24,069 passed and 7 skipped before an unrelated existing test_copy_targets.py import error; just check's code gates pass but SASE validation is blocked by existing missing plan/prompt links. git diff --check is clean.

## Dependencies

- **Depends on:** [sase-b1.1](sase-b1.1.md) ✓
- **Blocks:** [sase-b1.4](sase-b1.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b1.2/README.md) | [sase-b1.2](sase-b1.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0683114`](https://github.com/sase-org/sase/commit/068311411b65de0931d755cdfc88e66114a918b3) | feat(agent): carry swarm provenance through launches | [sase-b1.2](sase-b1.2.md) | 2026-07-30 01:57:40 |

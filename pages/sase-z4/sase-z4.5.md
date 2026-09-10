# Bead: sase-z4.5 — Adopt workload weights and complete the coordinated rollout

[Bead Pages](../README.md) / [sase-z4](README.md) / sase-z4.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0i5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0i5.md) · **Assignee:** `sase-z4.5` · **Size:** medium
**Created:** 2026-09-09 20:51:19 EDT · **Closed:** 2026-09-10 07:50:25 EDT
**Plan:** [202609/weighted\_queue\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_queue_capacity.md)

## Description

presets-rollout: apply 2.0 to bundled epic landers and 0.25 to all four research swarm segments, update documentation and package compatibility, exercise the integrated feature, and remove temporary rollout scaffolding.

## Notes

[2026-09-10T05:53:12Z · sase-z4.5] PROPOSED FOLLOW-UP: Publish weighted core/SASE release floor — `tools/probe_core_floor --sase-core-dir ... --json` reports `runner_capacity_snapshot`, `runner_capacity_policy_schema_version`, and `bind_batch_predecessor_waits` are only in unreleased core commits; after release, raise `sase-core-rs`/plugin floors to the actual published versions before plugin publication.

[2026-09-10T11:49:45Z · sase-z4.5] PROPOSED FOLLOW-UP: Close retired weighted_queue_capacity flag bead — this phase removed the Off branch and registry entry, but the phase-worker launch instructions authorized closing only sase-z4.5; land/triage should close existing flag bead sase-z5 or otherwise resolve it before the orphan grace window expires.

[2026-09-10T11:50:25Z · sase-z4.5] Verified queue weights are unconditional, bd/land_epic parses %q(w=2.0), research_swarm expands four %q(w=0.25) segments with default/no runners plus explicit runners=0, priority=0, and wait composition. Ran focused pytest (135 passed), main just check (passed; scoped lane escalated to full suite), research plugin just check and just test-wheel (passed), linked core terminology audit and just check with Python 3.14 LD_LIBRARY_PATH (passed), and epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-z4.4](sase-z4.4.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.5/README.md) | [sase-z4.5](sase-z4.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0afe85b`](https://github.com/sase-org/sase/commit/0afe85be475848d994eb78f622980097a017cbfb) | feat(xprompt): complete weighted queue rollout | [sase-z4.5](sase-z4.5.md) | 2026-09-10 07:52:27 EDT |

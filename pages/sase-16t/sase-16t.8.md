# Bead: sase-16t.8 — One engine for every jump, plus the end-to-end matrix

[Bead Pages](../README.md) / [sase-16t](README.md) / sase-16t.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pq.md) · **Assignee:** `sase-16t.8` · **Size:** medium
**Created:** 2026-09-23 08:23:38 EDT · **Closed:** 2026-09-23 13:57:33 EDT
**Plan:** [202609/artifact\_link\_jumps.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_jumps.md)

## Description

entry-points: route relation-panel misses and cross-pane relation jumps through the engine, fix `job:` jumps hidden by a collapsed scheduler fold and unconfigured provider kinds, and add a Links-panel-driven end-to-end test matrix covering every artifact kind.

## Notes

[2026-09-23T17:56:16Z · sase-16t.8] PROPOSED FOLLOW-UP: just check symvision flags ClanSummaryDigest in prompt_panel/_agent_tribe_clan_summaries.py (from e1c4208cd, unrelated to entry-points); needs owner triage

[2026-09-23T17:57:33Z · sase-16t.8] Verified: relation-panel misses and cross-pane jumps route through _follow_artifacts_target (Patches keeps its lens); job: chops expand service:scheduler and roll back on failure; unconfigured ref:* reports unified failure without landing on Stitches; Links-panel matrix (17 tests: bead phase/epic/task, agent hood, file, stitch, archived plan, filtered patch, chop trail, dangling, real $0 key path) green plus relation/link-follow/bounded suites green; just check blocked only by pre-existing symvision flag on ClanSummaryDigest (filed as follow-up); jump path adds no UI-thread I/O (hydration via to_thread, member_count in-memory)

## Dependencies

- **Depends on:** [sase-16t.5](sase-16t.5.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-16t.6](sase-16t.6.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-16t.7](sase-16t.7.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16t.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.8/README.md) | [sase-16t.8](sase-16t.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e3c2a77`](https://github.com/sase-org/sase/commit/e3c2a7788b83873dc1cdf5e8ca4da5bb381a7b04) | feat(ace): one engine for every jump, plus the end-to-end matrix | [sase-16t.8](sase-16t.8.md) | 2026-09-23 13:58:56 EDT |

# Bead: sase-tw.4 — Links follow renames instead of dangling

[Bead Pages](../README.md) / [sase-tw](README.md) / sase-tw.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.4` · **Size:** medium
**Created:** 2026-08-25 15:34:37 EDT · **Closed:** 2026-08-25 18:29:34 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

rename-following: consume git rename detection in the sidecar link refresh so a moved artifact carries its rows and its `links/` companion, then repair every dangling ref and orphaned companion the research workflow has already created.

## Notes

[2026-08-25T20:52:51Z · sase-tw.4] PROPOSED FOLLOW-UP: repair non-rename artifact-link health leftovers — after research rename repair, doctor reports dangling=0 but still reports 19 plan-side orphaned links/ indexes with no git rename history and 3 missing screenshot companions.

[2026-08-25T22:29:04Z · sase-tw.4] PROPOSED FOLLOW-UP: repair remaining non-rename artifact-link health leftovers - after rename repair and aggregate cleanup, direct link-health still reports dangling bead:sase-om, dangling research:202608/standalone_agent_cli_mode/standalone_agent_cli_mode.md with no exact git rename history, 19 plan orphaned links indexes, and stale research:202608/artifact_link_graph/artifact_link_graph.md projection.

[2026-08-25T22:29:34Z · sase-tw.4] Implemented rename-following refresh and historical repair; verified no epic-symbol entries, 58 focused tests passed, just check passed after full-suite escalation, and direct link-health after repair has dangling plan refs=0 with remaining non-rename leftovers recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-tw.1](sase-tw.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.7](sase-tw.7.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.4/README.md) | [sase-tw.4](sase-tw.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`678988d`](https://github.com/sase-org/sase/commit/678988da73439c5c552fcf26a4007f6fcd6a27f6) | fix(artifact-links): follow sidecar renames | [sase-tw.4](sase-tw.4.md) | 2026-08-25 18:33:35 EDT |
| sase--research | [`sase--research@1ecda82`](https://github.com/sase-org/sase--research/commit/1ecda82d17d2859476d90de64e89706d6d76c6a2) | fix(research): repair artifact link indexes | [sase-tw.4](sase-tw.4.md) | 2026-08-25 18:41:21 EDT |

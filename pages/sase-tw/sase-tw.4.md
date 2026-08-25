# Bead: sase-tw.4 — Links follow renames instead of dangling

[Bead Pages](../README.md) / [sase-tw](README.md) / sase-tw.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.4` · **Size:** medium
**Created:** 2026-08-25 15:34:37 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

rename-following: consume git rename detection in the sidecar link refresh so a moved artifact carries its rows and its `links/` companion, then repair every dangling ref and orphaned companion the research workflow has already created.

## Notes

[2026-08-25T20:52:51Z · sase-tw.4] PROPOSED FOLLOW-UP: repair non-rename artifact-link health leftovers — after research rename repair, doctor reports dangling=0 but still reports 19 plan-side orphaned links/ indexes with no git rename history and 3 missing screenshot companions.

[2026-08-25T22:29:04Z · sase-tw.4] PROPOSED FOLLOW-UP: repair remaining non-rename artifact-link health leftovers - after rename repair and aggregate cleanup, direct link-health still reports dangling bead:sase-om, dangling research:202608/standalone_agent_cli_mode/standalone_agent_cli_mode.md with no exact git rename history, 19 plan orphaned links indexes, and stale research:202608/artifact_link_graph/artifact_link_graph.md projection.

## Dependencies

- **Depends on:** [sase-tw.1](sase-tw.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.7](sase-tw.7.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.4/README.md) | [sase-tw.4](sase-tw.4.md) | 0 |

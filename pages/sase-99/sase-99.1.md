# Bead: sase-99.1 — Lane identity, lane fold scale, and the shared neighbor projection

[Bead Pages](../README.md) / [sase-99](README.md) / sase-99.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-99.1` · **Size:** medium
**Created:** 2026-07-25 12:39:48 UTC
**Plan:** [202607/lane\_neighbors\_section.md](https://github.com/sase-org/sase--plans/blob/main/202607/lane_neighbors_section.md)

## Description

'Phase lane-model' section: add `agent_owns_lane`, a lane fold scale helper, and a pure `AgentLaneNeighborProjection` builder, then refactor the `~` neighbors modal to build its choices from that same projection so the panel section and the modal can never drift.

## Notes

COMMIT: 1d6c95e60

## Dependencies

- **Blocks:** [sase-99.3](sase-99.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-99.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-99.1/README.md) | [sase-99.1](sase-99.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`1d6c95e`](https://github.com/sase-org/sase/commit/1d6c95e60d6ae0f98c309de41490aa4c8738a9d9) | refactor(ace): share lane neighbor projection (sase-99.1) | [sase-99.1](sase-99.1.md) | 2026-07-25 13:34:08 |

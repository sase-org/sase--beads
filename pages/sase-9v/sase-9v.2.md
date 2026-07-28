# Bead: sase-9v.2 — Always commit retained claims and make release outcomes tri-state

[Bead Pages](../README.md) / [sase-9v](README.md) / sase-9v.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9v.2` · **Size:** medium
**Created:** 2026-07-26 15:32:09 UTC
**Plan:** [sase/repos/plans/202607/bead\_review\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/bead_review_hardening.md)

## Description

claim_persistence: commit and publish a wait claim that is held but still uncommitted after a retry, return distinct released/no-op/error outcomes from claim release so shutdown can clear markers on no-ops, guard home-mode and in-tree claim publication, and enforce the push path's never-raises contract.

## Dependencies

- **Blocks:** [sase-9v.3](sase-9v.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9v.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9v.2/README.md) | [sase-9v.2](sase-9v.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a91b71d`](https://github.com/sase-org/sase/commit/a91b71d3702a24a8dde5a1a1fb0f8c811bc4f143) | fix(beads): persist and safely release waiting claims (sase-9v.2) | [sase-9v.2](sase-9v.2.md) | 2026-07-26 16:17:13 |

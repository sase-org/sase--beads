# Bead: sase-tw.7 — Derive at creation, on sidecar commit, and in the hourly sweep

[Bead Pages](../README.md) / [sase-tw](README.md) / sase-tw.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.7` · **Size:** medium
**Created:** 2026-08-25 15:34:40 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

derivation-hooks: call the derivation module from `sase plan propose` and `sase artifact create`, from the sidecar commit path for artifacts that land another way, and from a new `sase_chop_artifact_link_backfill` chop in the hourly housekeeping bucket that runs the retroactive sweep.

## Dependencies

- **Depends on:** [sase-tw.2](sase-tw.2.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tw.4](sase-tw.4.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tw.6](sase-tw.6.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.8](sase-tw.8.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.7/README.md) | [sase-tw.7](sase-tw.7.md) | 0 |

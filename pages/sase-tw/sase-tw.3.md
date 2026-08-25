# Bead: sase-tw.3 — A bead in either endpoint position gets its event

[Bead Pages](../README.md) / [sase-tw](README.md) / sase-tw.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.3` · **Size:** medium
**Created:** 2026-08-25 15:34:36 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

bead-endpoints: teach the sase-core bead link wire a direction, fire `_upsert_bead` when the bead is the target as well as the source, backfill the endpoint events one-sided writes never produced, and make `sase artifact create --bead` write a typed link with `reference_added` kept as a legacy alias.

## Dependencies

- **Depends on:** [sase-tw.1](sase-tw.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.6](sase-tw.6.md) ◐ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.9](sase-tw.9.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.3/README.md) | [sase-tw.3](sase-tw.3.md) | 0 |

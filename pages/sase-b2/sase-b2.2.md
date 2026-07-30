# Bead: sase-b2.2 — Local resolution and reverse canonicalization

[Bead Pages](../README.md) / [sase-b2](README.md) / sase-b2.2

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b2.2` · **Size:** medium
**Created:** 2026-07-30 01:33:17 UTC
**Plan:** [202607/bead\_and\_agent\_artifact\_refs.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_and_agent_artifact_refs.md)

## Description

core_resolve: extend `ArtifactRefContextWire` with bead stores, agent roots, and the local agent owner; port bead page addressing into Rust; implement `resolve_bead`/`resolve_agent` and the path-to-reference reverse mappings in `canonicalize_artifact_ref`.

## Dependencies

- **Depends on:** [sase-b2.1](sase-b2.1.md) ✓
- **Blocks:** [sase-b2.3](sase-b2.3.md) ◐
- **Blocks:** [sase-b2.4](sase-b2.4.md) ◐

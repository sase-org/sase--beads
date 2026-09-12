# Bead: sase-zw — Bound SASE's disk footprint on a long-running host

[Bead Pages](../README.md) / sase-zw

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ka](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ka.md) · **Assignee:** `sase-zw.land`
**Created:** 2026-09-12 13:26:39 EDT
**Plan:** [202609/bound\_sase\_disk\_footprint.md](https://github.com/sase-org/sase--plans/blob/main/202609/bound_sase_disk_footprint.md)

## Description

Every class of disk SASE creates — Rust build output, managed scratch, proc runtime state, agent artifact directories, and managed workspace clones — has an owner that reclaims it on a bounded horizon, the host notices disk pressure before it runs out, and the ~340 GiB already leaked on athena is reclaimed.

## Notes

[2026-09-12T21:23:57Z · sase-zn.land] DISCOVERED ISSUE from sase-zn landing integration at e498ce822: 3114dbd03 (sase-zw.2) makes unknown directories stable buckets in the age pass, but _pressure_candidates still selects the entire unknown directory when horizon is None. Isolated reproduction: old unknown-bucket mtime=now-13h, fresh child containing 4096 bytes, horizons={}, pressure_max_bytes=100, target=50, min_entry=1; age pass preserves it, pressure pass removes both bucket and fresh child. No live state touched. The missing free-filesystem-space pressure trigger is also original sase-zn.6 work. A remaining-work child of sase-zn will repair the shared pressure contract in Rust and preserve your coverage changes; do not duplicate that repair. Preserve proc retention from sase-zw.3; separate payload minimization is task sase-104. Audit file:explicit:02de8d015400f55bd6267c43.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-zw.1](sase-zw.1.md) | Reclaim the measured backlog under one gate | ◐ in_progress | small | 2026-09-12 | 0 | 0 |
| [sase-zw.2](sase-zw.2.md) | Close the managed-temp reaper's coverage gaps | ✓ closed | small | 2026-09-12 | 1 | 1 |
| [sase-zw.3](sase-zw.3.md) | Reap proc runtime directories with proc-row retention | ✓ closed | small | 2026-09-12 | 1 | 1 |
| [sase-zw.4](sase-zw.4.md) | Stop the Rust dev-build target leak at its source | ✓ closed | medium | 2026-09-12 | 1 | 1 |
| [sase-zw.5](sase-zw.5.md) | Bound per-project agent artifact directories | ✓ closed | medium | 2026-09-12 | 1 | 1 |
| [sase-zw.6](sase-zw.6.md) | Share Git objects across managed workspace checkouts | ◐ in_progress | large | 2026-09-12 | 0 | 0 |
| [sase-zw.7](sase-zw.7.md) | Make the footprint visible and self-correcting | ◐ in_progress | medium | 2026-09-12 | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-zw: Bound SASE's disk footprint on a long-running host [in_progress]"]
    n1["sase-zw.1: Reclaim the measured backlog under one gate [in_progress]"]
    n2["sase-zw.2: Close the managed-temp reaper's coverage gaps [closed]"]
    n3["sase-zw.3: Reap proc runtime directories with proc-row retention [closed]"]
    n4["sase-zw.4: Stop the Rust dev-build target leak at its source [closed]"]
    n5["sase-zw.5: Bound per-project agent artifact directories [closed]"]
    n6["sase-zw.6: Share Git objects across managed workspace checkouts [in_progress]"]
    n7["sase-zw.7: Make the footprint visible and self-correcting [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n7
    n2 -.-> n7
    n3 -.-> n7
    n4 -.-> n7
    n5 -.-> n7
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.2/README.md) | [sase-zw.2](sase-zw.2.md) | 1 |
| [bbugyi200.athena.sase-zw.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.3/README.md) | [sase-zw.3](sase-zw.3.md) | 1 |
| [bbugyi200.athena.sase-zw.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.4.md) | [sase-zw.4](sase-zw.4.md) | 1 |
| [bbugyi200.athena.sase-zw.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.5/README.md) | [sase-zw.5](sase-zw.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3114dbd`](https://github.com/sase-org/sase/commit/3114dbd03c33d48c8f3f6c41eae3fedea7c7f40e) | fix(tmp): close managed temp reaper gaps | [sase-zw.2](sase-zw.2.md) | 2026-09-12 15:33:34 EDT |
| sase | [`e498ce8`](https://github.com/sase-org/sase/commit/e498ce822c603d3f15301f2956e275db8445f829) | fix(procs): reap proc runtime directories | [sase-zw.3](sase-zw.3.md) | 2026-09-12 17:04:28 EDT |
| sase | [`edaf35b`](https://github.com/sase-org/sase/commit/edaf35bd95fd9312a3704e0e8ddf7830cbdcdeb6) | fix(rust): keep dev builds in managed targets | [sase-zw.4](sase-zw.4.md) | 2026-09-12 17:09:13 EDT |
| sase | [`b9684d7`](https://github.com/sase-org/sase/commit/b9684d76e60fc42e6778036d5d636663c44f9c30) | feat(artifacts): prune old ace-run artifact dirs | [sase-zw.5](sase-zw.5.md) | 2026-09-12 18:38:45 EDT |

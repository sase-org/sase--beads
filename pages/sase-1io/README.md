# Bead: sase-1io — Turn CI green and ship sase v0.18.0 to PyPI

[Bead Pages](../README.md) / sase-1io

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ys](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ys.md) · **Assignee:** `sase-1io.land`
**Created:** 2026-10-09 03:55:08 EDT
**Plan:** [202610/release\_v0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_v0_18_0.md)

## Description

Every sase and sase-core CI lane is green, a sase-core-rs release carrying every binding sase needs is on PyPI, the release-please PR merges, and `pip install sase==0.18.0` works from PyPI by morning.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1io.1](sase-1io.1.md) | Fix the red sase-core master CI | ✓ closed | medium | 2026-10-09 | 1 | 1 |
| [sase-1io.2](sase-1io.2.md) | Cut and publish the sase-core-rs release | ◐ in_progress | medium | 2026-10-09 | 1 | 0 |
| [sase-1io.3](sase-1io.3.md) | Fix the sase Master Gate failures | ◐ in_progress | medium | 2026-10-09 | 1 | 0 |
| [sase-1io.4](sase-1io.4.md) | Fix the Full CI-only failures | ◐ in_progress | medium | 2026-10-09 | 1 | 0 |
| [sase-1io.5](sase-1io.5.md) | Prove every release gate green | ◐ in_progress | medium | 2026-10-09 | 1 | 0 |
| [sase-1io.6](sase-1io.6.md) | Merge the release PR and publish v0.18.0 | ◐ in_progress | medium | 2026-10-09 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1io: Turn CI green and ship sase v0.18.0 to PyPI [in_progress]"]
    n1["sase-1io.1: Fix the red sase-core master CI [closed]"]
    n2["sase-1io.2: Cut and publish the sase-core-rs release [in_progress]"]
    n3["sase-1io.3: Fix the sase Master Gate failures [in_progress]"]
    n4["sase-1io.4: Fix the Full CI-only failures [in_progress]"]
    n5["sase-1io.5: Prove every release gate green [in_progress]"]
    n6["sase-1io.6: Merge the release PR and publish v0.18.0 [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n2 -.-> n5
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.1/README.md) | [sase-1io.1](sase-1io.1.md) | 1 |
| [bbugyi200.athena.sase-1io.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.2/README.md) | [sase-1io.2](sase-1io.2.md) | 0 |
| [bbugyi200.athena.sase-1io.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.3/README.md) | [sase-1io.3](sase-1io.3.md) | 0 |
| [bbugyi200.athena.sase-1io.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.4/README.md) | [sase-1io.4](sase-1io.4.md) | 0 |
| [bbugyi200.athena.sase-1io.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.5/README.md) | [sase-1io.5](sase-1io.5.md) | 0 |
| [bbugyi200.athena.sase-1io.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.6/README.md) | [sase-1io.6](sase-1io.6.md) | 0 |
| [bbugyi200.athena.sase-1io.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.land/README.md) | [sase-1io](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ce85b67`](https://github.com/sase-org/sase-core/commit/ce85b670e96c7b6dfd92dd1e897cf45c254a36ec) | fix(bead-tests): pin lock\_wait\_ms to zero in replay goldens | [sase-1io.1](sase-1io.1.md) | 2026-10-09 04:19:27 EDT |

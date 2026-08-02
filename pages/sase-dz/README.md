# Bead: sase-dz — Restore green CI on master

[Bead Pages](../README.md) / sase-dz

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rm](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rm/README.md) · **Assignee:** `sase-dz.land`
**Created:** 2026-08-02 10:45:39 UTC
**Plan:** [202608/ci\_green\_restoration.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_green_restoration.md)

## Description

A master CI run finishes with every job green: the published-core minimum smoke passes, `just validate` passes on a clean CI host, the bead ANSI snapshot matches in every environment, and all three test-matrix legs finish inside their timeout.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-dz.1](sase-dz.1.md) | Raise the published sase-core-rs floor to 0.17.8 | ✓ closed | small | 1 | 1 |
| [sase-dz.2](sase-dz.2.md) | Make bead prose highlighting ignore ambient NO\_COLOR | ✓ closed | small | 1 | 1 |
| [sase-dz.3](sase-dz.3.md) | Fit the test matrix inside its job timeout | ◐ in_progress | small | 1 | 0 |
| [sase-dz.4](sase-dz.4.md) | Skip the prompt-archive check when its context is unavailable | ✓ closed | medium | 1 | 1 |
| [sase-dz.5](sase-dz.5.md) | Publish the plans-sidecar prompt migration | ✓ closed | medium | 1 | 0 |
| [sase-dz.6](sase-dz.6.md) | Confirm a fully green master run | ◐ in_progress | small | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-dz: Restore green CI on master [in_progress]"]
    n1["sase-dz.1: Raise the published sase-core-rs floor to 0.17.8 [closed]"]
    n2["sase-dz.2: Make bead prose highlighting ignore ambient NO_COLOR [closed]"]
    n3["sase-dz.3: Fit the test matrix inside its job timeout [in_progress]"]
    n4["sase-dz.4: Skip the prompt-archive check when its context is unavailable [closed]"]
    n5["sase-dz.5: Publish the plans-sidecar prompt migration [closed]"]
    n6["sase-dz.6: Confirm a fully green master run [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n6
    n2 -.-> n6
    n3 -.-> n6
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dz.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.1/README.md) | [sase-dz.1](sase-dz.1.md) | 1 |
| [bbugyi200.athena.sase-dz.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.2/README.md) | [sase-dz.2](sase-dz.2.md) | 1 |
| [bbugyi200.athena.sase-dz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.3/README.md) | [sase-dz.3](sase-dz.3.md) | 0 |
| [bbugyi200.athena.sase-dz.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.4/README.md) | [sase-dz.4](sase-dz.4.md) | 1 |
| [bbugyi200.athena.sase-dz.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.5/README.md) | [sase-dz.5](sase-dz.5.md) | 0 |
| [bbugyi200.athena.sase-dz.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.6/README.md) | [sase-dz.6](sase-dz.6.md) | 0 |
| [bbugyi200.athena.sase-dz.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.land/README.md) | [sase-dz](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`a7ac9cc`](https://github.com/sase-org/sase/commit/a7ac9cc9af0e7e720d4303a7cef934c5e623f829) | fix(bead): force color in prose rendering so --color always beats NO\_COLOR | [sase-dz.2](sase-dz.2.md) | 2026-08-02 10:58:22 |
| sase | [`10843b5`](https://github.com/sase-org/sase/commit/10843b52209eb76d35040b3212800fe2e5cfd66b) | build(deps): raise sase-core-rs floor to 0.17.8 | [sase-dz.1](sase-dz.1.md) | 2026-08-02 11:09:11 |
| sase | [`404fac3`](https://github.com/sase-org/sase/commit/404fac3b5dfcd4bd069a6f94a1a1f37f1435cffc) | fix(validation): skip unavailable prompt archive context | [sase-dz.4](sase-dz.4.md) | 2026-08-02 11:19:38 |

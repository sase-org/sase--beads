# Bead: sase-am — CI flakiness redesign

[Bead Pages](../README.md) / sase-am

**Status:** ◎ claimed · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-am.land`
**Created:** 2026-07-28 22:05:46 UTC
**Plan:** [202607/ci\_flakiness\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202607/ci_flakiness_redesign.md)

## Description

Every started master CI run completes with trustworthy results: no starvation-by-cancellation, one Rust build per run, no duplicated or drift-prone lanes, and no loss of meaningful coverage.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-am.1](sase-am.1.md) | Restore completed-run signal and unbreak lint | ✓ closed | small | 1 | 1 |
| [sase-am.2](sase-am.2.md) | Build the Rust core once per run | ✓ closed | medium | 1 | 1 |
| [sase-am.3](sase-am.3.md) | Consolidate lanes without losing coverage | ✓ closed | medium | 1 | 1 |
| [sase-am.4](sase-am.4.md) | Derive the CI sidecar environment from configuration | ◎ claimed | small | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-am: CI flakiness redesign [claimed]"]
    n1["sase-am.1: Restore completed-run signal and unbreak lint [closed]"]
    n2["sase-am.2: Build the Rust core once per run [closed]"]
    n3["sase-am.3: Consolidate lanes without losing coverage [closed]"]
    n4["sase-am.4: Derive the CI sidecar environment from configuration [claimed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-am.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-am.1/README.md) | [sase-am.1](sase-am.1.md) | 1 |
| [bbugyi200.athena.sase-am.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-am.2/README.md) | [sase-am.2](sase-am.2.md) | 1 |
| [bbugyi200.athena.sase-am.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-am.3/README.md) | [sase-am.3](sase-am.3.md) | 1 |
| [bbugyi200.athena.sase-am.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-am.4/README.md) | [sase-am.4](sase-am.4.md) | 0 |
| [bbugyi200.athena.sase-am.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-am.land/README.md) | [sase-am](README.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`4d55dab`](https://github.com/sase-org/sase/commit/4d55dabc17152d033c195fcebdf21df4e16b2170) | ci: restore completed-run signal and unbreak lint | [sase-am.1](sase-am.1.md) | 2026-07-28 22:17:35 |
| [`61c812a`](https://github.com/sase-org/sase/commit/61c812a7b7f1e04c44e50330f803868154500e3d) | ci: reuse one prebuilt core wheel across jobs | [sase-am.2](sase-am.2.md) | 2026-07-28 22:39:22 |
| [`29ca9ac`](https://github.com/sase-org/sase/commit/29ca9ac511433323f872213603b1ead19db565c3) | ci: consolidate workflow lanes | [sase-am.3](sase-am.3.md) | 2026-07-28 23:04:01 |

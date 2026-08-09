# Bead: sase-ij — Ratchet the sase-core-rs window at the release boundary instead of on feature PRs

[Bead Pages](../README.md) / sase-ij

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.land`
**Created:** 2026-08-09 15:17:19 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

A feature agent can call a newly landed sase-core binding or behavior without editing pyproject.toml, uv.lock, or a version literal, and without waiting on a core release; the published-floor invariant is enforced once, mechanically, on the pending sase release instead of ~1.2 times a day by a dedicated agent.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-ij.1](sase-ij.1.md) | Derive the telemetry smoke test's expected minimum from pyproject | ✓ closed | small | 2026-08-09 | 1 | 0 |
| [sase-ij.2](sase-ij.2.md) | Build the window ratchet tool | ◐ in_progress | medium | 2026-08-09 | 1 | 0 |
| [sase-ij.3](sase-ij.3.md) | Enforce the published floor on the release branch and at publish time | ✓ closed | medium | 2026-08-09 | 1 | 0 |
| [sase-ij.4](sase-ij.4.md) | Ratchet the window on the pending release branch in report-only mode | ◐ in_progress | medium | 2026-08-09 | 1 | 0 |
| [sase-ij.5](sase-ij.5.md) | Verify one report-only run and switch the ratchet to apply | ◐ in_progress | small | 2026-08-09 | 1 | 0 |
| [sase-ij.6](sase-ij.6.md) | Stop conscripting feature agents into the floor bump | ◐ in_progress | small | 2026-08-09 | 1 | 0 |
| [sase-ij.7](sase-ij.7.md) | Add a non-fatal core-floor probe to just check | ◐ in_progress | medium | 2026-08-09 | 1 | 0 |
| [sase-ij.8](sase-ij.8.md) | Merge sase-core release PRs from the release-plz workflow | ◐ in_progress | small | 2026-08-09 | 1 | 2 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ij: Ratchet the sase-core-rs window at the release boundary instead of on feature PRs [in_progress]"]
    n1["sase-ij.1: Derive the telemetry smoke test's expected minimum from pyproject [closed]"]
    n2["sase-ij.2: Build the window ratchet tool [in_progress]"]
    n3["sase-ij.3: Enforce the published floor on the release branch and at publish time [closed]"]
    n4["sase-ij.4: Ratchet the window on the pending release branch in report-only mode [in_progress]"]
    n5["sase-ij.5: Verify one report-only run and switch the ratchet to apply [in_progress]"]
    n6["sase-ij.6: Stop conscripting feature agents into the floor bump [in_progress]"]
    n7["sase-ij.7: Add a non-fatal core-floor probe to just check [in_progress]"]
    n8["sase-ij.8: Merge sase-core release PRs from the release-plz workflow [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n2
    n2 -.-> n4
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.1/README.md) | [sase-ij.1](sase-ij.1.md) | 0 |
| [bbugyi200.athena.sase-ij.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.2/README.md) | [sase-ij.2](sase-ij.2.md) | 0 |
| [bbugyi200.athena.sase-ij.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.3/README.md) | [sase-ij.3](sase-ij.3.md) | 0 |
| [bbugyi200.athena.sase-ij.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.4/README.md) | [sase-ij.4](sase-ij.4.md) | 0 |
| [bbugyi200.athena.sase-ij.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.5/README.md) | [sase-ij.5](sase-ij.5.md) | 0 |
| [bbugyi200.athena.sase-ij.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.6/README.md) | [sase-ij.6](sase-ij.6.md) | 0 |
| [bbugyi200.athena.sase-ij.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.7/README.md) | [sase-ij.7](sase-ij.7.md) | 0 |
| [bbugyi200.athena.sase-ij.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.8/README.md) | [sase-ij.8](sase-ij.8.md) | 2 |
| [bbugyi200.athena.sase-ij.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.land/README.md) | [sase-ij](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@735a01b`](https://github.com/sase-org/sase-core/commit/735a01b35143a5208af83451af31996a325fd755) | ci(release-plz): auto-merge release PRs once checks pass | [sase-ij.8](sase-ij.8.md) | 2026-08-09 15:31:05 EDT |
| sase-core | [`sase-core@443f1aa`](https://github.com/sase-org/sase-core/commit/443f1aa16994eb840c032e99df449170f22c722e) | fix(release-plz): set GH\_REPO in the merge job's gh commands | [sase-ij.8](sase-ij.8.md) | 2026-08-09 15:44:57 EDT |

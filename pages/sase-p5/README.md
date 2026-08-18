# Bead: sase-p5 — Commit finalizer stops failing agents whose work actually landed

[Bead Pages](../README.md) / sase-p5

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05d](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05d.md) · **Assignee:** `sase-p5.land`
**Created:** 2026-08-17 18:55:29 EDT
**Plan:** [202608/commit\_finalizer\_attribution.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_finalizer_attribution.md)

## Description

An agent whose work is committed and pushed is never marked FAILED by the commit finalizer's discarded-work guard. Commit provenance survives conflict resolution, the finalizer decides attribution from evidence the run itself owns rather than from commit-message footers alone, and a concurrent agent's activity in a shared clone can no longer be misread as this agent discarding its work.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-p5.1](sase-p5.1.md) | Make the SASE commit footer survive conflict resolution | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p5.2](sase-p5.2.md) | Record a run-owned commit ledger | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p5.3](sase-p5.3.md) | Decide attribution from run-owned evidence | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p5.4](sase-p5.4.md) | Stop blaming an agent for concurrent activity in shared clones | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p5.5](sase-p5.5.md) | Actionable diagnostics and regression coverage | ◐ in_progress | small | 2026-08-17 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-p5: Commit finalizer stops failing agents whose work actually landed [in_progress]"]
    n1["sase-p5.1: Make the SASE commit footer survive conflict resolution [closed]"]
    n2["sase-p5.2: Record a run-owned commit ledger [closed]"]
    n3["sase-p5.3: Decide attribution from run-owned evidence [closed]"]
    n4["sase-p5.4: Stop blaming an agent for concurrent activity in shared clones [closed]"]
    n5["sase-p5.5: Actionable diagnostics and regression coverage [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p5.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p5.1.md) | [sase-p5.1](sase-p5.1.md) | 1 |
| [bbugyi200.athena.sase-p5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p5.2/README.md) | [sase-p5.2](sase-p5.2.md) | 1 |
| [bbugyi200.athena.sase-p5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p5.3/README.md) | [sase-p5.3](sase-p5.3.md) | 1 |
| [bbugyi200.athena.sase-p5.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p5.4.md) | [sase-p5.4](sase-p5.4.md) | 1 |
| [bbugyi200.athena.sase-p5.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p5.5/README.md) | [sase-p5.5](sase-p5.5.md) | 0 |
| [bbugyi200.athena.sase-p5.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p5.land/README.md) | [sase-p5](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`22e5444`](https://github.com/sase-org/sase/commit/22e5444bf29cdb1b964831c02678155911463689) | fix(commit): restamp dropped SASE footer tags on resumed commits | [sase-p5.1](sase-p5.1.md) | 2026-08-17 19:47:33 EDT |
| sase | [`1519d20`](https://github.com/sase-org/sase/commit/1519d20f27d69c164bf33e503e8af31ce65a4708) | feat(commit): record a run-owned commit ledger | [sase-p5.2](sase-p5.2.md) | 2026-08-17 21:02:26 EDT |
| sase | [`0d36217`](https://github.com/sase-org/sase/commit/0d36217142f100ab232b5567d0ad5e0c6fcc2706) | feat(commit): attribute discarded commits via run-owned ledger | [sase-p5.3](sase-p5.3.md) | 2026-08-17 21:24:04 EDT |
| sase | [`aaa09eb`](https://github.com/sase-org/sase/commit/aaa09eba9f945ac86cfd9faca2aae2e1d72159e4) | fix(llm\_provider): exempt shared-clone races from the discarded-work guard | [sase-p5.4](sase-p5.4.md) | 2026-08-18 06:48:02 EDT |

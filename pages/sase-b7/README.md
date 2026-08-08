# Bead: sase-b7 — Make artifact capture mean authorship and stop copying what version control stores

[Bead Pages](../README.md) / sase-b7

**Status:** ◐ in_progress · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b7.land`
**Created:** 2026-07-30 12:52:41 UTC
**Plan:** [202607/vcs\_backed\_artifact\_capture.md](https://github.com/sase-org/sase--plans/blob/main/202607/vcs_backed_artifact_capture.md)

## Description

Automatic artifact capture keeps bytes only for files an agent authored that version control cannot reproduce. Files that version control can reproduce get a byte-free record carrying repo, commit, and path provenance, and every reader — CLI, Files pane, and prompt `@`-ref expansion — can still get their exact content on demand.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-b7.1](sase-b7.1.md) | Rust core: VCS-backed records and on-demand materialization | ✓ closed | medium | 1 | 1 |
| [sase-b7.2](sase-b7.2.md) | Capture policy — the authorship and version-control decision | ✓ closed | medium | 1 | 1 |
| [sase-b7.3](sase-b7.3.md) | Python record, doctor, and read surfaces | ✓ closed | medium | 1 | 1 |
| [sase-b7.4](sase-b7.4.md) | Wire the policy into finalization capture | ✓ closed | small | 1 | 1 |
| [sase-b7.5](sase-b7.5.md) | Docs, skill, and configuration reference | ✓ closed | small | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-b7: Make artifact capture mean authorship and stop copying what version control stores [in_progress]"]
    n1["sase-b7.1: Rust core: VCS-backed records and on-demand materialization [closed]"]
    n2["sase-b7.2: Capture policy — the authorship and version-control decision [closed]"]
    n3["sase-b7.3: Python record, doctor, and read surfaces [closed]"]
    n4["sase-b7.4: Wire the policy into finalization capture [closed]"]
    n5["sase-b7.5: Docs, skill, and configuration reference [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n3
    n2 -.-> n4
    n3 -.-> n4
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b7.1/README.md) | [sase-b7.1](sase-b7.1.md) | 1 |
| [bbugyi200.athena.sase-b7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b7.2/README.md) | [sase-b7.2](sase-b7.2.md) | 1 |
| [bbugyi200.athena.sase-b7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b7.3/README.md) | [sase-b7.3](sase-b7.3.md) | 1 |
| [bbugyi200.athena.sase-b7.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b7.4/README.md) | [sase-b7.4](sase-b7.4.md) | 1 |
| [bbugyi200.athena.sase-b7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b7.5/README.md) | [sase-b7.5](sase-b7.5.md) | 1 |
| [bbugyi200.athena.sase-b7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b7.land/README.md) | [sase-b7](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`d309f95`](https://github.com/sase-org/sase/commit/d309f95370d8ecd8bda05e89b3e80057d3d6ca94) | feat: add authorship-aware artifact capture policy | [sase-b7.2](sase-b7.2.md) | 2026-07-30 13:18:52 |
| sase-core | [`sase-core@ee287b0`](https://github.com/sase-org/sase-core/commit/ee287b0523c8d611e9ce7935fc2a534287b7b104) | feat!: materialize VCS-backed artifact files | [sase-b7.1](sase-b7.1.md) | 2026-07-30 13:22:25 |
| sase | [`c9edec5`](https://github.com/sase-org/sase/commit/c9edec56145a050d89ed18911c27f90831e7a9dc) | feat(artifacts): materialize VCS-backed files on demand | [sase-b7.3](sase-b7.3.md) | 2026-07-30 13:48:54 |
| sase | [`94daa1e`](https://github.com/sase-org/sase/commit/94daa1ebdcff2d3adf11c24599d04807f8a5a03a) | feat(artifacts): wire VCS-backed default capture | [sase-b7.4](sase-b7.4.md) | 2026-07-30 14:20:33 |
| sase | [`658e576`](https://github.com/sase-org/sase/commit/658e57696301cdab8119f77ef0ec1cd4fda16037) | docs(artifacts): document VCS-backed artifact files | [sase-b7.5](sase-b7.5.md) | 2026-07-30 14:33:01 |

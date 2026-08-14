# Bead: sase-m4 — Stabilize GitHub Actions

[Bead Pages](../README.md) / sase-m4

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01o.md) · **Assignee:** `sase-m4.land`
**Created:** 2026-08-14 14:19:38 EDT
**Plan:** [202608/stabilize\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202608/stabilize_github_actions.md)

## Description

Restore reliable passing CI, documentation, and publication workflows on the sase default branch

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-m4.1](sase-m4.1.md) | Repair core release floor ratcheting | ✓ closed | medium | 2026-08-14 | 1 | 1 |
| [sase-m4.2](sase-m4.2.md) | Repair strict PDF documentation export | ✓ closed | medium | 2026-08-14 | 1 | 1 |
| [sase-m4.3](sase-m4.3.md) | Fix deterministic test failures and the stalled test shard | ✓ closed | medium | 2026-08-14 | 1 | 1 |
| [sase-m4.4](sase-m4.4.md) | Reconcile ACE visual behavior and snapshots | ✓ closed | medium | 2026-08-14 | 1 | 1 |
| [sase-m4.5](sase-m4.5.md) | Resolve the artifact-scan performance failure | ✓ closed | small | 2026-08-14 | 1 | 1 |
| [sase-m4.6](sase-m4.6.md) | Integrate, exhaustively verify, and observe GitHub Actions | ✓ closed | medium | 2026-08-14 | 2 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-m4: Stabilize GitHub Actions [in_progress]"]
    n1["sase-m4.1: Repair core release floor ratcheting [closed]"]
    n2["sase-m4.2: Repair strict PDF documentation export [closed]"]
    n3["sase-m4.3: Fix deterministic test failures and the stalled test shard [closed]"]
    n4["sase-m4.4: Reconcile ACE visual behavior and snapshots [closed]"]
    n5["sase-m4.5: Resolve the artifact-scan performance failure [closed]"]
    n6["sase-m4.6: Integrate, exhaustively verify, and observe GitHub Actions [closed]"]
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
| [bbugyi200.athena.sase-m4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m4.1/README.md) | [sase-m4.1](sase-m4.1.md) | 1 |
| [bbugyi200.athena.sase-m4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m4.2/README.md) | [sase-m4.2](sase-m4.2.md) | 1 |
| [bbugyi200.athena.sase-m4.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m4.3/README.md) | [sase-m4.3](sase-m4.3.md) | 1 |
| [bbugyi200.athena.sase-m4.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m4.4/README.md) | [sase-m4.4](sase-m4.4.md) | 1 |
| [bbugyi200.athena.sase-m4.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m4.5/README.md) | [sase-m4.5](sase-m4.5.md) | 1 |
| [bbugyi200.athena.sase-m4.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m4.6.md) | [sase-m4.6](sase-m4.6.md) | 0 |
| [bbugyi200.athena.sase-m4.6--2--code](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m4.6--2--code/README.md) | [sase-m4.6](sase-m4.6.md) | 1 |
| [bbugyi200.athena.sase-m4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m4.land/README.md) | [sase-m4](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8dd33e5`](https://github.com/sase-org/sase/commit/8dd33e594b17d255d9b28e95fcadc8d64e75931a) | fix: validate core lock ratchets semantically | [sase-m4.1](sase-m4.1.md) | 2026-08-14 14:42:48 EDT |
| sase | [`7a6e004`](https://github.com/sase-org/sase/commit/7a6e00416f21519d27f4ff6ca0fa2970862f033a) | perf: recalibrate agent scan regression floor | [sase-m4.5](sase-m4.5.md) | 2026-08-14 14:43:50 EDT |
| sase | [`e394229`](https://github.com/sase-org/sase/commit/e394229545f158f4971eb69e697cbd24030e0f26) | fix(tests): repair a TabQuickStart lifecycle race and a punctuation-brittle assertion | [sase-m4.3](sase-m4.3.md) | 2026-08-14 15:03:25 EDT |
| sase | [`bc040fe`](https://github.com/sase-org/sase/commit/bc040fee5d4a7cb2ad98c104587fa42499d9e089) | test: load bundled ACE visual fonts via font\_files | [sase-m4.4](sase-m4.4.md) | 2026-08-14 15:08:50 EDT |
| sase | [`e4baf07`](https://github.com/sase-org/sase/commit/e4baf07717f5a9cb836316b8db5416d1af3f8096) | fix(docs): stop strict PDF export from fetching remote Google Fonts | [sase-m4.2](sase-m4.2.md) | 2026-08-14 15:11:11 EDT |
| sase | [`357c45c`](https://github.com/sase-org/sase/commit/357c45c7235f4d8f23539787dc16f4df41955470) | test(docs): skip pypdf-dependent docs-PDF test when pypdf is absent | [sase-m4.6](sase-m4.6.md) | 2026-08-14 16:34:52 EDT |

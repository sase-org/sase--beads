# Bead: sase-1vb — Green GitHub Actions for sase

[Bead Pages](../README.md) / sase-1vb

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ge](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ge.md) · **Assignee:** `sase-1vb.land`
**Created:** 2026-11-26 06:30:35 EST
**Plan:** [202611/green\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202611/green_github_actions.md)

## Description

Every red sase GitHub Actions workflow is green on the landed master tip or handed to a named owner with evidence, each traced to a root cause, with no raised timeouts, weakened assertions, or blindly regenerated goldens.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1vb.1](sase-1vb.1.md) | Send Rust the exact release-asset wire shape | ◐ in_progress | small | 2026-11-26 | 1 | 0 |
| [sase-1vb.2](sase-1vb.2.md) | Make bench\_bead.py runnable as a script again | ✓ closed | xsmall | 2026-11-26 | 1 | 1 |
| [sase-1vb.3](sase-1vb.3.md) | Clear the four globals that fail the test-cost leak gate | ◐ in_progress | medium | 2026-11-26 | 1 | 0 |
| [sase-1vb.4](sase-1vb.4.md) | Root-cause the flakes that turned recent master SHAs red | ◐ in_progress | medium | 2026-11-26 | 1 | 0 |
| [sase-1vb.5](sase-1vb.5.md) | Rebaseline the November golden drift after proving each change is intended | ◐ in_progress | medium | 2026-11-26 | 1 | 0 |
| [sase-1vb.6](sase-1vb.6.md) | Prove the workflows green on the landed tip | ◐ in_progress | small | 2026-11-26 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1vb: Green GitHub Actions for sase [in_progress]"]
    n1["sase-1vb.1: Send Rust the exact release-asset wire shape [in_progress]"]
    n2["sase-1vb.2: Make bench_bead.py runnable as a script again [closed]"]
    n3["sase-1vb.3: Clear the four globals that fail the test-cost leak gate [in_progress]"]
    n4["sase-1vb.4: Root-cause the flakes that turned recent master SHAs red [in_progress]"]
    n5["sase-1vb.5: Rebaseline the November golden drift after proving each change is intended [in_progress]"]
    n6["sase-1vb.6: Prove the workflows green on the landed tip [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n6
    n2 -.-> n6
    n3 -.-> n6
    n4 -.-> n5
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vb.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.1/README.md) | [sase-1vb.1](sase-1vb.1.md) | 0 |
| [bbugyi200.athena.sase-1vb.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.2/README.md) | [sase-1vb.2](sase-1vb.2.md) | 1 |
| [bbugyi200.athena.sase-1vb.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.3/README.md) | [sase-1vb.3](sase-1vb.3.md) | 0 |
| [bbugyi200.athena.sase-1vb.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.4/README.md) | [sase-1vb.4](sase-1vb.4.md) | 0 |
| [bbugyi200.athena.sase-1vb.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.5/README.md) | [sase-1vb.5](sase-1vb.5.md) | 0 |
| [bbugyi200.athena.sase-1vb.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.6/README.md) | [sase-1vb.6](sase-1vb.6.md) | 0 |
| [bbugyi200.athena.sase-1vb.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.land/README.md) | [sase-1vb](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a52d432`](https://github.com/sase-org/sase/commit/a52d4328e6878bdf243d0161a6b243a1aba1cbc6) | fix(perf): bootstrap sys.path in bench\_bead.py and add static guard | [sase-1vb.2](sase-1vb.2.md) | 2026-11-26 06:49:22 EST |

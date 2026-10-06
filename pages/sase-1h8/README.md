# Bead: sase-1h8 — Bead store performance: remove replay waste, add a Rust read model, take issues.jsonl off the commit path

[Bead Pages](../README.md) / sase-1h8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.land`
**Created:** 2026-10-06 18:59:27 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

Hot-path bead reads and writes stop scaling with closed history. Every recommendation in the bead-history research report is implemented: the measured waste is removed, a Rust-owned, disposable, fingerprint-validated read model serves current state, issues.jsonl leaves the per-mutation commit path, and the physical sealed-archive design sits behind measured triggers. No bead event is ever edited, compressed in place, or deleted.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1h8.1](sase-1h8.1.md) | Scaled-corpus bead benchmark harness | ◐ in_progress | medium | 2026-10-06 | 1 | 0 |
| [sase-1h8.10](sase-1h8.10.md) | Sealed-segment triggers and design | ◐ in_progress | small | 2026-10-06 | 1 | 0 |
| [sase-1h8.11](sase-1h8.11.md) | issues.jsonl off the per-mutation path | ◐ in_progress | medium | 2026-10-06 | 1 | 0 |
| [sase-1h8.12](sase-1h8.12.md) | Indexed queries over the read model | ◐ in_progress | medium | 2026-10-06 | 1 | 0 |
| [sase-1h8.13](sase-1h8.13.md) | Mutations load and write through the read model | ◐ in_progress | large | 2026-10-06 | 1 | 0 |
| [sase-1h8.14](sase-1h8.14.md) | History-independence acceptance gate | ◐ in_progress | medium | 2026-10-06 | 1 | 0 |
| [sase-1h8.2](sase-1h8.2.md) | Constant-cost artifact-link outbox append | ✓ closed | small | 2026-10-06 | 1 | 1 |
| [sase-1h8.3](sase-1h8.3.md) | Hidden-clone gc and bead push-log retention | ◐ in_progress | small | 2026-10-06 | 1 | 0 |
| [sase-1h8.4](sase-1h8.4.md) | One parse, one validation, no lockless-read deletes | ◐ in_progress | medium | 2026-10-06 | 1 | 0 |
| [sase-1h8.5](sase-1h8.5.md) | Store fingerprint binding and consumer migration | ◐ in_progress | medium | 2026-10-06 | 1 | 0 |
| [sase-1h8.6](sase-1h8.6.md) | TUI Beads and Plans pane refresh | ◐ in_progress | medium | 2026-10-06 | 1 | 0 |
| [sase-1h8.7](sase-1h8.7.md) | One store read per CLI command | ◐ in_progress | medium | 2026-10-06 | 1 | 0 |
| [sase-1h8.8](sase-1h8.8.md) | Read-model substrate, freshness protocol, and parity harness | ◐ in_progress | medium | 2026-10-06 | 1 | 0 |
| [sase-1h8.9](sase-1h8.9.md) | Snapshot-plus-tail incremental refresh | ◐ in_progress | medium | 2026-10-06 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1h8: Bead store performance: remove replay waste, add a Rust read model, take issues.jsonl off the commit path [in_progress]"]
    n1["sase-1h8.1: Scaled-corpus bead benchmark harness [in_progress]"]
    n2["sase-1h8.10: Sealed-segment triggers and design [in_progress]"]
    n3["sase-1h8.11: issues.jsonl off the per-mutation path [in_progress]"]
    n4["sase-1h8.12: Indexed queries over the read model [in_progress]"]
    n5["sase-1h8.13: Mutations load and write through the read model [in_progress]"]
    n6["sase-1h8.14: History-independence acceptance gate [in_progress]"]
    n7["sase-1h8.2: Constant-cost artifact-link outbox append [closed]"]
    n8["sase-1h8.3: Hidden-clone gc and bead push-log retention [in_progress]"]
    n9["sase-1h8.4: One parse, one validation, no lockless-read deletes [in_progress]"]
    n10["sase-1h8.5: Store fingerprint binding and consumer migration [in_progress]"]
    n11["sase-1h8.6: TUI Beads and Plans pane refresh [in_progress]"]
    n12["sase-1h8.7: One store read per CLI command [in_progress]"]
    n13["sase-1h8.8: Read-model substrate, freshness protocol, and parity harness [in_progress]"]
    n14["sase-1h8.9: Snapshot-plus-tail incremental refresh [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n0 --> n11
    n0 --> n12
    n0 --> n13
    n0 --> n14
    n1 -.-> n13
    n2 -.-> n6
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
    n7 -.-> n6
    n8 -.-> n6
    n9 -.-> n12
    n9 -.-> n13
    n10 -.-> n3
    n10 -.-> n11
    n11 -.-> n6
    n12 -.-> n3
    n12 -.-> n4
    n13 -.-> n3
    n13 -.-> n14
    n14 -.-> n2
    n14 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.1/README.md) | [sase-1h8.1](sase-1h8.1.md) | 0 |
| [bbugyi200.athena.sase-1h8.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.10/README.md) | [sase-1h8.10](sase-1h8.10.md) | 0 |
| [bbugyi200.athena.sase-1h8.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.11/README.md) | [sase-1h8.11](sase-1h8.11.md) | 0 |
| [bbugyi200.athena.sase-1h8.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.12/README.md) | [sase-1h8.12](sase-1h8.12.md) | 0 |
| [bbugyi200.athena.sase-1h8.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13/README.md) | [sase-1h8.13](sase-1h8.13.md) | 0 |
| [bbugyi200.athena.sase-1h8.14](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.14/README.md) | [sase-1h8.14](sase-1h8.14.md) | 0 |
| [bbugyi200.athena.sase-1h8.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.2.md) | [sase-1h8.2](sase-1h8.2.md) | 1 |
| [bbugyi200.athena.sase-1h8.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.3.md) | [sase-1h8.3](sase-1h8.3.md) | 0 |
| [bbugyi200.athena.sase-1h8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.4/README.md) | [sase-1h8.4](sase-1h8.4.md) | 0 |
| [bbugyi200.athena.sase-1h8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.5/README.md) | [sase-1h8.5](sase-1h8.5.md) | 0 |
| [bbugyi200.athena.sase-1h8.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.6/README.md) | [sase-1h8.6](sase-1h8.6.md) | 0 |
| [bbugyi200.athena.sase-1h8.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.7/README.md) | [sase-1h8.7](sase-1h8.7.md) | 0 |
| [bbugyi200.athena.sase-1h8.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.8/README.md) | [sase-1h8.8](sase-1h8.8.md) | 0 |
| [bbugyi200.athena.sase-1h8.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.9/README.md) | [sase-1h8.9](sase-1h8.9.md) | 0 |
| [bbugyi200.athena.sase-1h8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.land/README.md) | [sase-1h8](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`545caa7`](https://github.com/sase-org/sase/commit/545caa7abdfb746e83900b2fc1590f40635783d2) | feat(outbox): constant-cost artifact-link outbox append (sase-1h8.2) | [sase-1h8.2](sase-1h8.2.md) | 2026-10-06 19:28:48 EDT |

# Bead: sase-b4 — Gate \`@\` reference file rows behind kind misses and explicit Ctrl+T

[Bead Pages](../README.md) / sase-b4

**Status:** ◐ in_progress · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b4.land`
**Created:** 2026-07-30 11:14:59 UTC
**Plan:** [202607/at\_reference\_file\_row\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202607/at_reference_file_row_gate.md)

## Description

The grouped `@` reference menu lists local file rows only when no artifact kind prefix-matches the typed text, or when the user explicitly asks for them (`Ctrl+T` in the ACE prompt, a manually invoked completion request over LSP). The rule is decided once in the shared Rust core so the TUI and every LSP client agree.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-b4.1](sase-b4.1.md) | Shared kind-stage file-row gate in sase-core | ✓ closed | medium | 1 | 0 |
| [sase-b4.2](sase-b4.2.md) | ACE prompt gating and the Ctrl+T reveal | ✓ closed | medium | 1 | 1 |
| [sase-b4.3](sase-b4.3.md) | Raise the sase-core-rs floor and verify end to end | ◐ in_progress | xsmall | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-b4: Gate `@` reference file rows behind kind misses and explicit Ctrl+T [in_progress]"]
    n1["sase-b4.1: Shared kind-stage file-row gate in sase-core [closed]"]
    n2["sase-b4.2: ACE prompt gating and the Ctrl+T reveal [closed]"]
    n3["sase-b4.3: Raise the sase-core-rs floor and verify end to end [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n1 -.-> n2
    n1 -.-> n3
    n2 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b4.1/README.md) | [sase-b4.1](sase-b4.1.md) | 0 |
| [bbugyi200.athena.sase-b4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b4.2/README.md) | [sase-b4.2](sase-b4.2.md) | 1 |
| [bbugyi200.athena.sase-b4.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b4.3/README.md) | [sase-b4.3](sase-b4.3.md) | 0 |
| [bbugyi200.athena.sase-b4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b4.land/README.md) | [sase-b4](README.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`9ba92b0`](https://github.com/sase-org/sase/commit/9ba92b09a7cacd192f59ccc0756970d8ca67526d) | feat(ace): gate artifact file completion rows | [sase-b4.2](sase-b4.2.md) | 2026-07-30 11:47:37 |

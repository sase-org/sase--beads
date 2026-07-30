# Bead: sase-b2 — Add \`@bead:\` and \`@agent:\` artifact reference kinds

[Bead Pages](../README.md) / sase-b2

**Status:** ◐ in_progress · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b2.land`
**Created:** 2026-07-30 01:33:06 UTC
**Plan:** [202607/bead\_and\_agent\_artifact\_refs.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_and_agent_artifact_refs.md)

## Description

`@bead:sase-9z` and `@agent:9w` are first-class artifact references everywhere the existing four builtin kinds already work — prompt expansion, `sase artifact show/path/open`, the ACE `@` menu and prompt highlighting, the LSP, and ACE copy mode — resolving through generated bead and agent pages with loud, actionable diagnostics when a page has not been published yet.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-b2.1](sase-b2.1.md) | Bead and agent reference grammar in sase-core | ✓ closed | small | 1 | 1 |
| [sase-b2.2](sase-b2.2.md) | Local resolution and reverse canonicalization | ✓ closed | medium | 1 | 1 |
| [sase-b2.3](sase-b2.3.md) | Editor surfaces for the new kinds | ✓ closed | small | 1 | 1 |
| [sase-b2.4](sase-b2.4.md) | Python models and resolution context | ◐ in_progress | medium | 0 | 0 |
| [sase-b2.5](sase-b2.5.md) | Prompt expansion and \`sase artifact\` support | ◐ in_progress | small | 0 | 0 |
| [sase-b2.6](sase-b2.6.md) | ACE \`@\` menu payload rows for beads and agents | ◐ in_progress | medium | 0 | 0 |
| [sase-b2.7](sase-b2.7.md) | ACE copy mode yields bead and agent references | ◐ in_progress | medium | 0 | 0 |
| [sase-b2.8](sase-b2.8.md) | Documentation sweep | ◐ in_progress | small | 0 | 0 |
| [sase-b2.9](sase-b2.9.md) | Raise the published \`sase-core-rs\` floor | ◐ in_progress | small | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-b2: Add `@bead:` and `@agent:` artifact reference kinds [in_progress]"]
    n1["sase-b2.1: Bead and agent reference grammar in sase-core [closed]"]
    n2["sase-b2.2: Local resolution and reverse canonicalization [closed]"]
    n3["sase-b2.3: Editor surfaces for the new kinds [closed]"]
    n4["sase-b2.4: Python models and resolution context [in_progress]"]
    n5["sase-b2.5: Prompt expansion and `sase artifact` support [in_progress]"]
    n6["sase-b2.6: ACE `@` menu payload rows for beads and agents [in_progress]"]
    n7["sase-b2.7: ACE copy mode yields bead and agent references [in_progress]"]
    n8["sase-b2.8: Documentation sweep [in_progress]"]
    n9["sase-b2.9: Raise the published `sase-core-rs` floor [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n1 -.-> n2
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n8
    n4 -.-> n5
    n4 -.-> n6
    n5 -.-> n8
    n6 -.-> n7
    n7 -.-> n8
    n8 -.-> n9
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-b2.1 | [sase-b2.1](sase-b2.1.md) | 1 |
| bbugyi200.athena.sase-b2.2 | [sase-b2.2](sase-b2.2.md) | 1 |
| bbugyi200.athena.sase-b2.3 | [sase-b2.3](sase-b2.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`c1ae5f5`](https://github.com/sase-org/sase-core/commit/c1ae5f55f85b93658588eb90a700d5fa5c5054cb) | feat(artifact-ref): add bead and agent reference grammar | [sase-b2.1](sase-b2.1.md) | 2026-07-30 01:48:13 |
| [`858d24c`](https://github.com/sase-org/sase-core/commit/858d24c8dddec225961734cfbd74bd37da2a976d) | feat(artifact-ref): resolve bead and agent page references | [sase-b2.2](sase-b2.2.md) | 2026-07-30 02:04:04 |
| [`aaa4e05`](https://github.com/sase-org/sase-core/commit/aaa4e0506fb4d1e5f84a8f71c715c3bb48b668d9) | feat(artifact-ref): complete bead and agent page references | [sase-b2.3](sase-b2.3.md) | 2026-07-30 02:12:58 |

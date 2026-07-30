# Bead: sase-b2 — Add \`@bead:\` and \`@agent:\` artifact reference kinds

[Bead Pages](../README.md) / sase-b2

**Status:** ✓ closed · **Resolution:** done · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b2.land`
**Created:** 2026-07-30 01:33:06 UTC · **Closed:** 2026-07-30 04:04:39 UTC
**Plan:** [202607/bead\_and\_agent\_artifact\_refs.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_and_agent_artifact_refs.md)

## Description

`@bead:sase-9z` and `@agent:9w` are first-class artifact references everywhere the existing four builtin kinds already work — prompt expansion, `sase artifact show/path/open`, the ACE `@` menu and prompt highlighting, the LSP, and ACE copy mode — resolving through generated bead and agent pages with loud, actionable diagnostics when a page has not been published yet.

## Notes

[2026-07-30T04:04:39Z · sase-b2.land] Fixed workspace-derived artifact-reference project resolution by preferring the project name, matching GitHub provider slugs across multi-project contexts, and logging best-effort inventory/entity lookup failures. Verified focused regression tests, live bead and agent page resolution, populated entity/repository context, and a green just check.

[2026-07-30T04:11:19Z · sase-b2.land] Finalizer reconfirmed live bead and agent artifact resolution; just check and standalone Symvision passed

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-b2.1](sase-b2.1.md) | Bead and agent reference grammar in sase-core | ✓ closed | small | 0 | 0 |
| [sase-b2.2](sase-b2.2.md) | Local resolution and reverse canonicalization | ✓ closed | medium | 0 | 0 |
| [sase-b2.3](sase-b2.3.md) | Editor surfaces for the new kinds | ✓ closed | small | 0 | 0 |
| [sase-b2.4](sase-b2.4.md) | Python models and resolution context | ✓ closed | medium | 0 | 0 |
| [sase-b2.5](sase-b2.5.md) | Prompt expansion and \`sase artifact\` support | ✓ closed | small | 0 | 0 |
| [sase-b2.6](sase-b2.6.md) | ACE \`@\` menu payload rows for beads and agents | ✓ closed | medium | 0 | 0 |
| [sase-b2.7](sase-b2.7.md) | ACE copy mode yields bead and agent references | ✓ closed | medium | 0 | 0 |
| [sase-b2.8](sase-b2.8.md) | Documentation sweep | ✓ closed | small | 0 | 0 |
| [sase-b2.9](sase-b2.9.md) | Raise the published \`sase-core-rs\` floor | ✓ closed | small | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-b2: Add `@bead:` and `@agent:` artifact reference kinds [closed]"]
    n1["sase-b2.1: Bead and agent reference grammar in sase-core [closed]"]
    n2["sase-b2.2: Local resolution and reverse canonicalization [closed]"]
    n3["sase-b2.3: Editor surfaces for the new kinds [closed]"]
    n4["sase-b2.4: Python models and resolution context [closed]"]
    n5["sase-b2.5: Prompt expansion and `sase artifact` support [closed]"]
    n6["sase-b2.6: ACE `@` menu payload rows for beads and agents [closed]"]
    n7["sase-b2.7: ACE copy mode yields bead and agent references [closed]"]
    n8["sase-b2.8: Documentation sweep [closed]"]
    n9["sase-b2.9: Raise the published `sase-core-rs` floor [closed]"]
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
| bbugyi200.athena.sase-b2.land--code | [sase-b2](README.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`89a96ab`](https://github.com/sase-org/sase--plans/commit/89a96ab7fa7298cca69dc69a62259461019c27be) | docs: mark bead and agent artifact plan done | [sase-b2](README.md) | 2026-07-30 04:13:10 |

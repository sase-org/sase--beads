# Bead: sase-js — Artifact reference contract

[Bead Pages](../README.md) / sase-js

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.y2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.y2/README.md) · **Assignee:** `sase-js.land`
**Created:** 2026-08-11 13:20:33 EDT
**Plan:** [202608/artifact\_ref\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_contract.md)

## Description

Artifact references stop being xprompts and become a first-class, versioned ref contract: five builtin kinds (`@stitch`, `@patch`, `@bead`, `@agent`, `@file`) plus artifact-repo document kinds (`@plan`, `@research`, ...) configured inline or with `use: <provider>` from an installed plugin. Every ref expands deterministically, is recorded per occurrence against the agent that used it, publishes as a numbered Markdown reference link, writes a `Referenced By` table back into the cited artifact, and gets a generated "Artifacts" sub-tab in ACE.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-js.1](sase-js.1.md) | Ref contract wire types in sase-core | ✓ closed | large | 2026-08-11 | 1 | 2 |
| [sase-js.2](sase-js.2.md) | Retire the ref xprompt surface | ✓ closed | medium | 2026-08-11 | 1 | 2 |
| [sase-js.3](sase-js.3.md) | Provider registry, plugin hooks, and config | ✓ closed | large | 2026-08-11 | 1 | 1 |
| [sase-js.4](sase-js.4.md) | Builtin refs and prompt ref context | ◐ in_progress | large | 2026-08-11 | 1 | 0 |
| [sase-js.5](sase-js.5.md) | The @file ref and the content-addressed store | ◐ in_progress | large | 2026-08-11 | 1 | 0 |
| [sase-js.6](sase-js.6.md) | Reference links and Referenced By write-back | ◐ in_progress | large | 2026-08-11 | 1 | 0 |
| [sase-js.7](sase-js.7.md) | Generated Artifacts sub-tabs and the new Files pane | ◐ in_progress | large | 2026-08-11 | 1 | 0 |
| [sase-js.8](sase-js.8.md) | The sase-research plugin repository | ◐ in_progress | large | 2026-08-11 | 1 | 0 |
| [sase-js.9](sase-js.9.md) | Adoption, glossary, and documentation | ◐ in_progress | medium | 2026-08-11 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-js: Artifact reference contract [in_progress]"]
    n1["sase-js.1: Ref contract wire types in sase-core [closed]"]
    n2["sase-js.2: Retire the ref xprompt surface [closed]"]
    n3["sase-js.3: Provider registry, plugin hooks, and config [closed]"]
    n4["sase-js.4: Builtin refs and prompt ref context [in_progress]"]
    n5["sase-js.5: The @file ref and the content-addressed store [in_progress]"]
    n6["sase-js.6: Reference links and Referenced By write-back [in_progress]"]
    n7["sase-js.7: Generated Artifacts sub-tabs and the new Files pane [in_progress]"]
    n8["sase-js.8: The sase-research plugin repository [in_progress]"]
    n9["sase-js.9: Adoption, glossary, and documentation [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n1 -.-> n3
    n2 -.-> n3
    n3 -.-> n4
    n3 -.-> n5
    n3 -.-> n8
    n4 -.-> n6
    n4 -.-> n7
    n5 -.-> n6
    n5 -.-> n7
    n6 -.-> n9
    n7 -.-> n9
    n8 -.-> n9
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-js.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-js.1.md) | [sase-js.1](sase-js.1.md) | 2 |
| [bbugyi200.athena.sase-js.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-js.2/README.md) | [sase-js.2](sase-js.2.md) | 2 |
| [bbugyi200.athena.sase-js.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-js.3.md) | [sase-js.3](sase-js.3.md) | 1 |
| [bbugyi200.athena.sase-js.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-js.4/README.md) | [sase-js.4](sase-js.4.md) | 0 |
| [bbugyi200.athena.sase-js.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-js.5/README.md) | [sase-js.5](sase-js.5.md) | 0 |
| [bbugyi200.athena.sase-js.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-js.6/README.md) | [sase-js.6](sase-js.6.md) | 0 |
| [bbugyi200.athena.sase-js.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-js.7/README.md) | [sase-js.7](sase-js.7.md) | 0 |
| [bbugyi200.athena.sase-js.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-js.8/README.md) | [sase-js.8](sase-js.8.md) | 0 |
| [bbugyi200.athena.sase-js.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-js.9/README.md) | [sase-js.9](sase-js.9.md) | 0 |
| [bbugyi200.athena.sase-js.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-js.land/README.md) | [sase-js](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3cc5af7`](https://github.com/sase-org/sase-core/commit/3cc5af750182a7b54bb3b61dae6e2465794f0bf7) | feat(artifact-ref)!: add ref contract wire types, quoted arguments, link allocator, and Referenced By block | [sase-js.1](sase-js.1.md) | 2026-08-11 14:30:55 EDT |
| sase | [`cb453a5`](https://github.com/sase-org/sase/commit/cb453a529e483d4237afdfab66fd2be9e1caadeb) | feat(artifact-ref)!: bump wire schema to 5 for stitch/patch/file-path kinds | [sase-js.1](sase-js.1.md) | 2026-08-11 15:16:10 EDT |
| sase | [`e2cacbe`](https://github.com/sase-org/sase/commit/e2cacbe34ce16e3df92dc390ea11376972da5c77) | refactor(xprompt)!: retire the #ref/\<kind\> contextual renderer adapter | [sase-js.2](sase-js.2.md) | 2026-08-11 15:33:12 EDT |
| sase-core | [`sase-core@c0f1ca4`](https://github.com/sase-org/sase-core/commit/c0f1ca43cfa83eda2e91bb4902c132aaacfaecfe) | refactor(core)!: retire the #ref/\<kind\> xprompt-catalog adapter | [sase-js.2](sase-js.2.md) | 2026-08-11 15:34:43 EDT |
| sase | [`f53e43a`](https://github.com/sase-org/sase/commit/f53e43ab139a7db2c50b75971fb7a5fc202619e5) | feat!: add artifact provider registry | [sase-js.3](sase-js.3.md) | 2026-08-11 16:21:40 EDT |

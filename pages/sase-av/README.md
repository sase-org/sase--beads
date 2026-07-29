# Bead: sase-av — Kind-tagged artifact references and prompt-bar integration

[Bead Pages](../README.md) / sase-av

**Status:** ◐ in_progress · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-av.land`
**Created:** 2026-07-29 16:44:54 UTC
**Plan:** [202607/artifact\_refs\_and\_prompt\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_refs_and_prompt_bar.md)

## Description

One reference grammar names every artifact SASE knows: `plans:` generalizes into `<kind>:<payload>` references covering commits, chats, bugs, artifact files, and every configured document-sidecar role, owned by the Rust core and spent in the ACE copy menus, the prompt bar (highlighted, completed, and expanded at launch), and external editors through LSP completion, diagnostics, and semantic tokens.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-av.1](sase-av.1.md) | Kind-tagged artifact reference grammar in the Rust core | ✓ closed | large | 1 | 1 |
| [sase-av.2](sase-av.2.md) | Python artifact-reference facade and context resolution | ✓ closed | medium | 0 | 0 |
| [sase-av.3](sase-av.3.md) | Copy and hand off references from the Artifacts sub-tabs | ✓ closed | medium | 0 | 0 |
| [sase-av.4](sase-av.4.md) | Recognize and expand artifact references at launch | ✓ closed | medium | 0 | 0 |
| [sase-av.5](sase-av.5.md) | Artifact-reference highlighting in the prompt input widget | ✓ closed | medium | 0 | 0 |
| [sase-av.6](sase-av.6.md) | Artifact-reference completion in the prompt bar | ◐ in_progress | large | 0 | 0 |
| [sase-av.7](sase-av.7.md) | Artifact-reference completion and diagnostics in the xprompt LSP | ✓ closed | large | 1 | 1 |
| [sase-av.8](sase-av.8.md) | Semantic-token highlighting for artifact references in editors | ◐ in_progress | medium | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-av: Kind-tagged artifact references and prompt-bar integration [in_progress]"]
    n1["sase-av.1: Kind-tagged artifact reference grammar in the Rust core [closed]"]
    n2["sase-av.2: Python artifact-reference facade and context resolution [closed]"]
    n3["sase-av.3: Copy and hand off references from the Artifacts sub-tabs [closed]"]
    n4["sase-av.4: Recognize and expand artifact references at launch [closed]"]
    n5["sase-av.5: Artifact-reference highlighting in the prompt input widget [closed]"]
    n6["sase-av.6: Artifact-reference completion in the prompt bar [in_progress]"]
    n7["sase-av.7: Artifact-reference completion and diagnostics in the xprompt LSP [closed]"]
    n8["sase-av.8: Semantic-token highlighting for artifact references in editors [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n2
    n1 -.-> n7
    n2 -.-> n3
    n2 -.-> n4
    n2 -.-> n5
    n2 -.-> n6
    n2 -.-> n7
    n5 -.-> n6
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-av.1--code | [sase-av.1](sase-av.1.md) | 1 |
| bbugyi200.athena.sase-av.7--code | [sase-av.7](sase-av.7.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`6c2adc4`](https://github.com/sase-org/sase-core/commit/6c2adc420a5ee24aecfe5fae305e2c869ab7b627) | feat: add core artifact reference APIs | [sase-av.1](sase-av.1.md) | 2026-07-29 17:15:02 |
| [`334b987`](https://github.com/sase-org/sase-core/commit/334b987ae09afc5960ae9f4728c9803088839f60) | feat(editor): complete artifact references in xprompt LSP | [sase-av.7](sase-av.7.md) | 2026-07-29 19:02:38 |

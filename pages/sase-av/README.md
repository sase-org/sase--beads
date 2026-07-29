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
| [sase-av.1](sase-av.1.md) | Kind-tagged artifact reference grammar in the Rust core | ✓ closed | large | 2 | 0 |
| [sase-av.2](sase-av.2.md) | Python artifact-reference facade and context resolution | ✓ closed | medium | 1 | 1 |
| [sase-av.3](sase-av.3.md) | Copy and hand off references from the Artifacts sub-tabs | ✓ closed | medium | 1 | 1 |
| [sase-av.4](sase-av.4.md) | Recognize and expand artifact references at launch | ✓ closed | medium | 1 | 1 |
| [sase-av.5](sase-av.5.md) | Artifact-reference highlighting in the prompt input widget | ✓ closed | medium | 1 | 1 |
| [sase-av.6](sase-av.6.md) | Artifact-reference completion in the prompt bar | ✓ closed | large | 2 | 1 |
| [sase-av.7](sase-av.7.md) | Artifact-reference completion and diagnostics in the xprompt LSP | ✓ closed | large | 2 | 1 |
| [sase-av.8](sase-av.8.md) | Semantic-token highlighting for artifact references in editors | ◐ in_progress | medium | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-av: Kind-tagged artifact references and prompt-bar integration [in_progress]"]
    n1["sase-av.1: Kind-tagged artifact reference grammar in the Rust core [closed]"]
    n2["sase-av.2: Python artifact-reference facade and context resolution [closed]"]
    n3["sase-av.3: Copy and hand off references from the Artifacts sub-tabs [closed]"]
    n4["sase-av.4: Recognize and expand artifact references at launch [closed]"]
    n5["sase-av.5: Artifact-reference highlighting in the prompt input widget [closed]"]
    n6["sase-av.6: Artifact-reference completion in the prompt bar [closed]"]
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
| [bbugyi200.athena.sase-av.1--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-av.1.md#member-code) | [sase-av.1](sase-av.1.md) | 0 |
| [bbugyi200.athena.sase-av.1--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-av.1.md#member-plan) | [sase-av.1](sase-av.1.md) | 0 |
| [bbugyi200.athena.sase-av.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-av.2/README.md) | [sase-av.2](sase-av.2.md) | 1 |
| [bbugyi200.athena.sase-av.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-av.3/README.md) | [sase-av.3](sase-av.3.md) | 1 |
| [bbugyi200.athena.sase-av.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-av.4/README.md) | [sase-av.4](sase-av.4.md) | 1 |
| [bbugyi200.athena.sase-av.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-av.5/README.md) | [sase-av.5](sase-av.5.md) | 1 |
| [bbugyi200.athena.sase-av.6--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-av.6.md#member-code) | [sase-av.6](sase-av.6.md) | 1 |
| [bbugyi200.athena.sase-av.6--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-av.6.md#member-plan) | [sase-av.6](sase-av.6.md) | 0 |
| [bbugyi200.athena.sase-av.7--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-av.7.md#member-code) | [sase-av.7](sase-av.7.md) | 1 |
| [bbugyi200.athena.sase-av.7--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-av.7.md#member-plan) | [sase-av.7](sase-av.7.md) | 0 |
| [bbugyi200.athena.sase-av.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-av.8/README.md) | [sase-av.8](sase-av.8.md) | 0 |
| [bbugyi200.athena.sase-av.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-av.land/README.md) | [sase-av](README.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`9988b61`](https://github.com/sase-org/sase/commit/9988b6161c9b47b3a657b49981fb11b1bf3e0c98) | feat(artifacts): add artifact reference facade | [sase-av.2](sase-av.2.md) | 2026-07-29 17:52:13 |
| [`46b40c5`](https://github.com/sase-org/sase/commit/46b40c5f6610b2ccd97d0e315b853a6563b2ab1a) | feat(artifacts): expand references during prompt launch | [sase-av.4](sase-av.4.md) | 2026-07-29 18:25:21 |
| [`de57f5a`](https://github.com/sase-org/sase/commit/de57f5a5f3e8563b48400f2843737ef7b4c8b33b) | feat(tui): highlight artifact references in prompts | [sase-av.5](sase-av.5.md) | 2026-07-29 18:32:47 |
| [`d16fe1d`](https://github.com/sase-org/sase/commit/d16fe1dcd9abe1bcc0e6b44af0bc98e2b0ad5788) | feat(ace): copy artifact references from artifact tabs | [sase-av.3](sase-av.3.md) | 2026-07-29 18:38:57 |
| [`3f6e4ea`](https://github.com/sase-org/sase/commit/3f6e4ea81a0ea13d5f0427358df02aa0c5cdde0a) | feat(editor): materialize artifact reference catalog for LSP | [sase-av.7](sase-av.7.md) | 2026-07-29 19:03:40 |
| [`e55aab9`](https://github.com/sase-org/sase/commit/e55aab9c92f73f5f902fa58ee39641da6a78686a) | feat(ace): add artifact reference prompt completion | [sase-av.6](sase-av.6.md) | 2026-07-29 19:07:54 |

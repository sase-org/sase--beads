# Bead: sase-1if — Plugin commands — sase listen as the first first-class command plugin

[Bead Pages](../README.md) / sase-1if

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0n.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0n.linker.w0.md) · **Assignee:** `sase-1if.land`
**Created:** 2026-10-08 15:26:22 EDT
**Plan:** [202610/plugin\_commands.md](https://github.com/sase-org/sase--plans/blob/main/202610/plugin_commands.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/plugin_commands.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/plugin_commands.md

<!-- sase:links:end -->

## Description

Plugins can mount top-level `sase <name>` commands through a metadata-declared `sase_commands` entry point. sase-listen uses it to ship `sase listen`, which behaves exactly like `sase-listen`, completes in bash/zsh/fish and the TUI `:` line, refreshes completion automatically on every plugin change, and is installed and managed from the Admin Center's Updates tab. Every moment a plugin adds or removes a command is announced clearly and consistently.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1if.1](sase-1if.1.md) | Plugin command contract, discovery, and dispatch | ◐ in_progress | medium | 2026-10-08 | 1 | 0 |
| [sase-1if.10](sase-1if.10.md) | End-to-end acceptance, records, and docs | ◐ in_progress | medium | 2026-10-08 | 1 | 0 |
| [sase-1if.2](sase-1if.2.md) | sase-listen becomes a command plugin | ✓ closed | medium | 2026-10-08 | 1 | 0 |
| [sase-1if.3](sase-1if.3.md) | Plugin commands in root help and sase doctor | ◐ in_progress | small | 2026-10-08 | 1 | 0 |
| [sase-1if.4](sase-1if.4.md) | Plugin subtrees in completion with plugin-aware cache identity | ◐ in_progress | medium | 2026-10-08 | 1 | 0 |
| [sase-1if.5](sase-1if.5.md) | Command-aware plugin install, update, and uninstall | ◐ in_progress | medium | 2026-10-08 | 1 | 0 |
| [sase-1if.6](sase-1if.6.md) | Pre-install command preview | ◐ in_progress | small | 2026-10-08 | 1 | 0 |
| [sase-1if.7](sase-1if.7.md) | Commands in the Updates tab and plugin detail | ◐ in_progress | medium | 2026-10-08 | 1 | 0 |
| [sase-1if.8](sase-1if.8.md) | Lazy sase-listen command imports | ✓ closed | small | 2026-10-08 | 1 | 0 |
| [sase-1if.9](sase-1if.9.md) | Research macros prefer sase listen | ✓ closed | small | 2026-10-08 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1if: Plugin commands — sase listen as the first first-class command plugin [in_progress]"]
    n1["sase-1if.1: Plugin command contract, discovery, and dispatch [in_progress]"]
    n2["sase-1if.10: End-to-end acceptance, records, and docs [in_progress]"]
    n3["sase-1if.2: sase-listen becomes a command plugin [closed]"]
    n4["sase-1if.3: Plugin commands in root help and sase doctor [in_progress]"]
    n5["sase-1if.4: Plugin subtrees in completion with plugin-aware cache identity [in_progress]"]
    n6["sase-1if.5: Command-aware plugin install, update, and uninstall [in_progress]"]
    n7["sase-1if.6: Pre-install command preview [in_progress]"]
    n8["sase-1if.7: Commands in the Updates tab and plugin detail [in_progress]"]
    n9["sase-1if.8: Lazy sase-listen command imports [closed]"]
    n10["sase-1if.9: Research macros prefer sase listen [closed]"]
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
    n1 -.-> n4
    n1 -.-> n5
    n1 -.-> n6
    n3 -.-> n9
    n3 -.-> n10
    n4 -.-> n2
    n5 -.-> n6
    n6 -.-> n7
    n7 -.-> n8
    n8 -.-> n2
    n9 -.-> n2
    n10 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1if.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.1/README.md) | [sase-1if.1](sase-1if.1.md) | 0 |
| [bbugyi200.apollo.sase-1if.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.10/README.md) | [sase-1if.10](sase-1if.10.md) | 0 |
| [bbugyi200.apollo.sase-1if.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.2/README.md) | [sase-1if.2](sase-1if.2.md) | 0 |
| [bbugyi200.apollo.sase-1if.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.3/README.md) | [sase-1if.3](sase-1if.3.md) | 0 |
| [bbugyi200.apollo.sase-1if.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.4/README.md) | [sase-1if.4](sase-1if.4.md) | 0 |
| [bbugyi200.apollo.sase-1if.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.5/README.md) | [sase-1if.5](sase-1if.5.md) | 0 |
| [bbugyi200.apollo.sase-1if.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.6/README.md) | [sase-1if.6](sase-1if.6.md) | 0 |
| [bbugyi200.apollo.sase-1if.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.7/README.md) | [sase-1if.7](sase-1if.7.md) | 0 |
| [bbugyi200.apollo.sase-1if.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.8/README.md) | [sase-1if.8](sase-1if.8.md) | 0 |
| [bbugyi200.apollo.sase-1if.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.9/README.md) | [sase-1if.9](sase-1if.9.md) | 1 |
| [bbugyi200.apollo.sase-1if.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.land/README.md) | [sase-1if](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-research-artifacts | [`sase-research-artifacts@91e353c`](https://github.com/sase-org/sase-research-artifacts/commit/91e353c8d898b235f665382e5262f5d6cdba50df) | feat(research-artifacts): prefer sase listen CLI in audio and swarm prompts | [sase-1if.9](sase-1if.9.md) | 2026-10-08 16:32:18 EDT |

# Bead: sase-16n — Xprompt project tags (+sase)

[Bead Pages](../README.md) / sase-16n

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pl.md) · **Assignee:** `sase-16n.land`
**Created:** 2026-09-22 18:48:43 EDT
**Plan:** [202609/project\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags.md)

## Description

Prompts name their project with a `+<project>` project tag by default. SASE resolves the tag to the project's VCS type and runs the same `#gh:`/`#git:` workflow as before. Every completion surface (TUI, LSP/Neovim, shell) inserts tags. Every surface that shows raw prompts renders tags in the project's accent color. Project names are enforced unique, case-insensitively, across all VCS types.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-16n.1](sase-16n.1.md) | sase-core project tag lexer, resolver, expander, and bindings | ✓ closed | medium | 2026-09-22 | 1 | 1 |
| [sase-16n.10](sase-16n.10.md) | Docs, skills, memory, config, and machine verification | ◐ in_progress | medium | 2026-09-22 | 1 | 0 |
| [sase-16n.2](sase-16n.2.md) | Case-insensitive project name uniqueness across VCS types | ◐ in_progress | small | 2026-09-22 | 1 | 0 |
| [sase-16n.3](sase-16n.3.md) | Python project tag backend and launch integration | ◐ in_progress | medium | 2026-09-22 | 1 | 0 |
| [sase-16n.4](sase-16n.4.md) | sase-xprompt-lsp project tag support | ◐ in_progress | medium | 2026-09-22 | 1 | 0 |
| [sase-16n.5](sase-16n.5.md) | TUI prompt editor completion and tag defaults | ◐ in_progress | medium | 2026-09-22 | 1 | 0 |
| [sase-16n.6](sase-16n.6.md) | Tag rendering in the agent panel and prompt editor | ◐ in_progress | medium | 2026-09-22 | 1 | 0 |
| [sase-16n.7](sase-16n.7.md) | Accent-colored tags on every remaining raw-prompt surface | ◐ in_progress | medium | 2026-09-22 | 1 | 0 |
| [sase-16n.8](sase-16n.8.md) | sase-nvim project tag highlighting and picker | ◐ in_progress | small | 2026-09-22 | 1 | 0 |
| [sase-16n.9](sase-16n.9.md) | sase-telegram and sase-github tag adoption | ◐ in_progress | small | 2026-09-22 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-16n: Xprompt project tags (+sase) [in_progress]"]
    n1["sase-16n.1: sase-core project tag lexer, resolver, expander, and bindings [closed]"]
    n2["sase-16n.10: Docs, skills, memory, config, and machine verification [in_progress]"]
    n3["sase-16n.2: Case-insensitive project name uniqueness across VCS types [in_progress]"]
    n4["sase-16n.3: Python project tag backend and launch integration [in_progress]"]
    n5["sase-16n.4: sase-xprompt-lsp project tag support [in_progress]"]
    n6["sase-16n.5: TUI prompt editor completion and tag defaults [in_progress]"]
    n7["sase-16n.6: Tag rendering in the agent panel and prompt editor [in_progress]"]
    n8["sase-16n.7: Accent-colored tags on every remaining raw-prompt surface [in_progress]"]
    n9["sase-16n.8: sase-nvim project tag highlighting and picker [in_progress]"]
    n10["sase-16n.9: sase-telegram and sase-github tag adoption [in_progress]"]
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
    n3 -.-> n2
    n3 -.-> n4
    n4 -.-> n6
    n4 -.-> n9
    n5 -.-> n9
    n6 -.-> n2
    n6 -.-> n7
    n7 -.-> n8
    n7 -.-> n10
    n8 -.-> n2
    n9 -.-> n2
    n10 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.1/README.md) | [sase-16n.1](sase-16n.1.md) | 1 |
| [bbugyi200.athena.sase-16n.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.10/README.md) | [sase-16n.10](sase-16n.10.md) | 0 |
| [bbugyi200.athena.sase-16n.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.2/README.md) | [sase-16n.2](sase-16n.2.md) | 0 |
| [bbugyi200.athena.sase-16n.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.3/README.md) | [sase-16n.3](sase-16n.3.md) | 0 |
| [bbugyi200.athena.sase-16n.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.4/README.md) | [sase-16n.4](sase-16n.4.md) | 0 |
| [bbugyi200.athena.sase-16n.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.5/README.md) | [sase-16n.5](sase-16n.5.md) | 0 |
| [bbugyi200.athena.sase-16n.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.6/README.md) | [sase-16n.6](sase-16n.6.md) | 0 |
| [bbugyi200.athena.sase-16n.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.7/README.md) | [sase-16n.7](sase-16n.7.md) | 0 |
| [bbugyi200.athena.sase-16n.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.8/README.md) | [sase-16n.8](sase-16n.8.md) | 0 |
| [bbugyi200.athena.sase-16n.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.9/README.md) | [sase-16n.9](sase-16n.9.md) | 0 |
| [bbugyi200.athena.sase-16n.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.land/README.md) | [sase-16n](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@096d42a`](https://github.com/sase-org/sase-core/commit/096d42a3d80ecfc413ed3230e47940b99f3bc257) | feat(core-tags): add project\_tag scan/resolve/expand/accept with catalog wire v5 | [sase-16n.1](sase-16n.1.md) | 2026-09-22 19:45:03 EDT |

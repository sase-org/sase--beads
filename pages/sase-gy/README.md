# Bead: sase-gy — Make the Markdown prose width a config field and default it to 88

[Bead Pages](../README.md) / sase-gy

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-gt.land.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gt.land.f1/README.md) · **Assignee:** `sase-gy.land`
**Created:** 2026-08-07 10:25:07 EDT
**Plan:** [202608/configurable\_markdown\_print\_width.md](https://github.com/sase-org/sase--plans/blob/main/202608/configurable_markdown_print_width.md)

## Description

`markdown.print_width` is a first-class SASE config field that every Markdown-emitting code path resolves at runtime, its shipped default is 88 instead of 100, and the repo's own Markdown, generated artifacts, and dotfile formatter configuration all agree with the new default.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-gy.1](sase-gy.1.md) | Runtime-resolved \`markdown.print\_width\` config field | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-gy.2](sase-gy.2.md) | Flip the shipped default from 100 to 88 | ◐ in_progress | medium | 2026-08-07 | 1 | 0 |
| [sase-gy.3](sase-gy.3.md) | Align chezmoi's prettier and conform configuration with the new default | ◐ in_progress | small | 2026-08-07 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-gy: Make the Markdown prose width a config field and default it to 88 [in_progress]"]
    n1["sase-gy.1: Runtime-resolved `markdown.print_width` config field [closed]"]
    n2["sase-gy.2: Flip the shipped default from 100 to 88 [in_progress]"]
    n3["sase-gy.3: Align chezmoi's prettier and conform configuration with the new default [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n1 -.-> n2
    n2 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gy.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gy.1/README.md) | [sase-gy.1](sase-gy.1.md) | 1 |
| [bbugyi200.athena.sase-gy.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gy.2/README.md) | [sase-gy.2](sase-gy.2.md) | 0 |
| [bbugyi200.athena.sase-gy.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gy.3/README.md) | [sase-gy.3](sase-gy.3.md) | 0 |
| [bbugyi200.athena.sase-gy.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gy.land/README.md) | [sase-gy](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0bea680`](https://github.com/sase-org/sase/commit/0bea6801eace98ffcd0dd839434173d556633bda) | feat(config): add a runtime-resolved markdown.print\_width config field | [sase-gy.1](sase-gy.1.md) | 2026-08-07 10:55:17 EDT |

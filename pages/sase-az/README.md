# Bead: sase-az — Unified "Copy as…" palette

[Bead Pages](../README.md) / sase-az

**Status:** ◐ in_progress · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-az.land`
**Created:** 2026-07-29 23:12:27 UTC
**Plan:** [202607/copy\_as\_palette.md](https://github.com/sase-org/sase--plans/blob/main/202607/copy_as_palette.md)

## Description

Pressing the copy prefix anywhere in ACE opens one beautiful, discoverable "Copy as…" palette: every existing copy target keeps its key as an accelerator, new Markdown-link and metadata-JSON representations join the reference/path/contents targets, marked sets pluralize into paste-ready forms, the artifact-files modal gains the full file-kind representation set, and every copy in the TUI rides one delivery seam that pairs OSC 52 with the subprocess adapter, names exactly what was copied, and leaves the generated text selectable when no transport works.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-az.1](sase-az.1.md) | One clipboard delivery seam with OSC 52 and a selectable fallback | ✓ closed | medium | 1 | 1 |
| [sase-az.2](sase-az.2.md) | Representation targets and one copy-target registry | ✓ closed | medium | 1 | 1 |
| [sase-az.3](sase-az.3.md) | The Copy-as palette modal | ✓ closed | large | 2 | 1 |
| [sase-az.4](sase-az.4.md) | File-kind representations in the artifact-files modal | ◐ in_progress | medium | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-az: Unified \"Copy as…\" palette [in_progress]"]
    n1["sase-az.1: One clipboard delivery seam with OSC 52 and a selectable fallback [closed]"]
    n2["sase-az.2: Representation targets and one copy-target registry [closed]"]
    n3["sase-az.3: The Copy-as palette modal [closed]"]
    n4["sase-az.4: File-kind representations in the artifact-files modal [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-az.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-az.1/README.md) | [sase-az.1](sase-az.1.md) | 1 |
| [bbugyi200.athena.sase-az.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-az.2/README.md) | [sase-az.2](sase-az.2.md) | 1 |
| [bbugyi200.athena.sase-az.3--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-az.3.md#member-code) | [sase-az.3](sase-az.3.md) | 1 |
| [bbugyi200.athena.sase-az.3--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-az.3.md#member-plan) | [sase-az.3](sase-az.3.md) | 0 |
| [bbugyi200.athena.sase-az.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-az.4/README.md) | [sase-az.4](sase-az.4.md) | 0 |
| [bbugyi200.athena.sase-az.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-az.land/README.md) | [sase-az](README.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`77ec879`](https://github.com/sase-org/sase/commit/77ec8798e0c6f435e3b32a4f24e161ce268fb81f) | feat(ace): unify clipboard delivery | [sase-az.1](sase-az.1.md) | 2026-07-29 23:50:42 |
| [`cf844c3`](https://github.com/sase-org/sase/commit/cf844c3e5d574d7c8898a73fd36cba686c17a6ad) | feat(ace): add paste-ready copy representations | [sase-az.2](sase-az.2.md) | 2026-07-30 00:27:20 |
| [`3da9140`](https://github.com/sase-org/sase/commit/3da9140b4968f590f84ace1db91f21c565746381) | feat(ace): add contextual Copy as palette | [sase-az.3](sase-az.3.md) | 2026-07-30 01:14:52 |

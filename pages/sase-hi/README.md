# Bead: sase-hi — Singular xprompt skill references and builtin source exception

[Bead Pages](../README.md) / sase-hi

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-hf.land.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hf.land.w2/README.md) · **Assignee:** `sase-hi.land`
**Created:** 2026-08-08 11:49:49 EDT
**Plan:** [202608/xprompt\_skill\_singular\_namespace.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_skill_singular_namespace.md)

## Description

Xprompt-backed skills expand through the singular #skill/ namespace while user and plugin sources remain in plural skills/ directories and bundled Markdown skill sources live only under src/sase/xprompts/skills/.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-hi.1](sase-hi.1.md) | Shared skill reference and directory contracts | ✓ closed | medium | 2026-08-08 | 1 | 1 |
| [sase-hi.2](sase-hi.2.md) | Python builtin source layout and loading | ✓ closed | medium | 2026-08-08 | 1 | 1 |
| [sase-hi.3](sase-hi.3.md) | User-facing cutover and end-to-end verification | ◐ in_progress | medium | 2026-08-08 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-hi: Singular xprompt skill references and builtin source exception [in_progress]"]
    n1["sase-hi.1: Shared skill reference and directory contracts [closed]"]
    n2["sase-hi.2: Python builtin source layout and loading [closed]"]
    n3["sase-hi.3: User-facing cutover and end-to-end verification [in_progress]"]
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
| [bbugyi200.athena.sase-hi.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hi.1/README.md) | [sase-hi.1](sase-hi.1.md) | 1 |
| [bbugyi200.athena.sase-hi.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hi.2/README.md) | [sase-hi.2](sase-hi.2.md) | 1 |
| [bbugyi200.athena.sase-hi.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hi.3/README.md) | [sase-hi.3](sase-hi.3.md) | 0 |
| [bbugyi200.athena.sase-hi.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hi.land/README.md) | [sase-hi](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8a0db59`](https://github.com/sase-org/sase-core/commit/8a0db5999a9f4dd3a64031cf31ca994151535fc8) | feat!: use singular skill xprompt references | [sase-hi.1](sase-hi.1.md) | 2026-08-08 12:26:12 EDT |
| sase | [`92f0ff3`](https://github.com/sase-org/sase/commit/92f0ff3774ca867ee971cedb092045d2a4824262) | feat(xprompts): load bundled skills from xprompt resources | [sase-hi.2](sase-hi.2.md) | 2026-08-08 13:11:31 EDT |

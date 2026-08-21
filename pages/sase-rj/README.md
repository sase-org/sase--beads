# Bead: sase-rj — Complete xprompt directive completion in ACE and external editors

[Bead Pages](../README.md) / sase-rj

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08s](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08s.md) · **Assignee:** `sase-rj.land`
**Created:** 2026-08-20 13:44:18 EDT
**Plan:** [202608/xprompt\_directive\_completion\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_directive_completion_parity.md)

## Description

Give every supported xprompt directive, syntax form, keyword name, and useful keyword value one shared, responsive completion contract across the prompt input widget and the xprompt LSP.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-rj.1](sase-rj.1.md) | Canonical directive completion contract in sase-core | ✓ closed | medium | 2026-08-20 | 1 | 1 |
| [sase-rj.2](sase-rj.2.md) | Complete contextual directive support in the xprompt LSP | ✓ closed | medium | 2026-08-20 | 1 | 2 |
| [sase-rj.3](sase-rj.3.md) | Complete responsive directive support in the ACE prompt widget | ✓ closed | medium | 2026-08-20 | 1 | 1 |
| [sase-rj.4](sase-rj.4.md) | Lock runtime, widget, and LSP parity with tests and documentation | ✓ closed | medium | 2026-08-20 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-rj: Complete xprompt directive completion in ACE and external editors [in_progress]"]
    n1["sase-rj.1: Canonical directive completion contract in sase-core [closed]"]
    n2["sase-rj.2: Complete contextual directive support in the xprompt LSP [closed]"]
    n3["sase-rj.3: Complete responsive directive support in the ACE prompt widget [closed]"]
    n4["sase-rj.4: Lock runtime, widget, and LSP parity with tests and documentation [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n2
    n1 -.-> n3
    n2 -.-> n4
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rj.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rj.1/README.md) | [sase-rj.1](sase-rj.1.md) | 1 |
| [bbugyi200.athena.sase-rj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rj.2/README.md) | [sase-rj.2](sase-rj.2.md) | 2 |
| [bbugyi200.athena.sase-rj.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rj.3.md) | [sase-rj.3](sase-rj.3.md) | 1 |
| [bbugyi200.athena.sase-rj.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rj.4/README.md) | [sase-rj.4](sase-rj.4.md) | 1 |
| [bbugyi200.athena.sase-rj.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rj.land/README.md) | [sase-rj](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@04c27f2`](https://github.com/sase-org/sase-core/commit/04c27f2a22a9d1e621b6acec666789a3fb89395e) | feat(editor): add canonical xprompt directive completion contract | [sase-rj.1](sase-rj.1.md) | 2026-08-20 14:20:14 EDT |
| sase-core | [`sase-core@16b1594`](https://github.com/sase-org/sase-core/commit/16b15944e4fb5fd73c8a8e22d25d2fc6944708a6) | feat(editor): drive xprompt LSP directive completion from the shared contract | [sase-rj.2](sase-rj.2.md) | 2026-08-20 15:18:20 EDT |
| sase | [`eadc738`](https://github.com/sase-org/sase/commit/eadc7389ccee0b7ab73cb803bf6644216ecdaa57) | feat(editor): include bounded bead rows in helper-bridge agent-catalog | [sase-rj.2](sase-rj.2.md) | 2026-08-20 15:22:36 EDT |
| sase | [`1830524`](https://github.com/sase-org/sase/commit/1830524b09be6ce7c5e62ca007d400e8655734b7) | feat(ace): complete prompt-widget xprompt directive completion | [sase-rj.3](sase-rj.3.md) | 2026-08-20 15:52:16 EDT |
| sase | [`0e80b9f`](https://github.com/sase-org/sase/commit/0e80b9f96a6b4c599be747818e39894ff4319ef5) | fix(ace): omit model alias self references from completion | [sase-rj.4](sase-rj.4.md) | 2026-08-21 05:39:34 EDT |

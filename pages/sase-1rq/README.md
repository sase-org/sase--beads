# Bead: sase-1rq — Repair red GitHub Actions CI across five projects

[Bead Pages](../README.md) / sase-1rq

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19h.md) · **Assignee:** `sase-1rq.land`
**Created:** 2026-11-07 07:46:42 EST
**Plan:** [202611/red\_ci\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202611/red_ci_repair.md)

## Description

Every project whose GitHub Actions CI went red in the ~12 hours before 2026-11-07 07:30 EST (sase-core, sase, bob-cli, bob-mac-capture, dotfiles) is green at its default-branch tip, with machine-readable green evidence attached to the phase's final turn, or, after a very large and well-documented effort, carries a research-sidecar report that tells Bryan exactly what is still needed to finish.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1rq.1](sase-1rq.1.md) | Turn sase-core CI green and unblock its release | ◐ in_progress | xlarge | 2026-11-07 | 1 | 0 |
| [sase-1rq.2](sase-1rq.2.md) | Turn every red sase workflow green | ◐ in_progress | xlarge | 2026-11-07 | 1 | 0 |
| [sase-1rq.3](sase-1rq.3.md) | Turn bob-cli CI green | ◐ in_progress | xlarge | 2026-11-07 | 1 | 0 |
| [sase-1rq.4](sase-1rq.4.md) | Turn bob-mac-capture CI green | ◐ in_progress | xlarge | 2026-11-07 | 1 | 0 |
| [sase-1rq.5](sase-1rq.5.md) | Turn dotfiles CI green | ◐ in_progress | xlarge | 2026-11-07 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1rq: Repair red GitHub Actions CI across five projects [in_progress]"]
    n1["sase-1rq.1: Turn sase-core CI green and unblock its release [in_progress]"]
    n2["sase-1rq.2: Turn every red sase workflow green [in_progress]"]
    n3["sase-1rq.3: Turn bob-cli CI green [in_progress]"]
    n4["sase-1rq.4: Turn bob-mac-capture CI green [in_progress]"]
    n5["sase-1rq.5: Turn dotfiles CI green [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.1.md) | [sase-1rq.1](sase-1rq.1.md) | 0 |
| [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2/README.md) | [sase-1rq.2](sase-1rq.2.md) | 0 |
| [bbugyi200.athena.sase-1rq.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3/README.md) | [sase-1rq.3](sase-1rq.3.md) | 0 |
| [bbugyi200.athena.sase-1rq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.md) | [sase-1rq.4](sase-1rq.4.md) | 0 |
| [bbugyi200.athena.sase-1rq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.5.md) | [sase-1rq.5](sase-1rq.5.md) | 1 |
| [bbugyi200.athena.sase-1rq.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.land/README.md) | [sase-1rq](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@28fd5c7`](https://github.com/bbugyi200/dotfiles/commit/28fd5c78dac932cb948121b71823a3887a69a9aa) | fix(tests): use grep instead of rg in doctl\_login\_test | [sase-1rq.5](sase-1rq.5.md) | 2026-11-07 08:04:09 EST |

# Bead: sase-1qz — Agent Hijack: stop a stalled agent, keep its work, recover in one keypress

[Bead Pages](../README.md) / sase-1qz

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.33.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.33.linker.w0.md) · **Assignee:** `sase-1qz.land`
**Created:** 2026-11-02 17:42:13 EST
**Plan:** [202611/agent\_hijack.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md)

## Description

A user can hijack a stalled sase agent (,k, the kill dialog's h, or `sase agent hijack NAME`). Its process tree stops, but its workspace claim, Agents-tab node, and evidence stay. The node shows a ⏏ HIJACKED status, and <enter> opens a single-keypress recovery panel: escalate to a smarter model, continue, or instruct in the same workspace; restart or edit from a fresh workspace after a verified snapshot; view the diff, open a shell, or dismiss. Every path is durable, exactly-once, and fails closed so work is never silently lost.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1qz.1](sase-1qz.1.md) | sase-core: hijack statuses, ledger wire, and eligibility | ✓ closed | medium | 2026-11-02 | 1 | 2 |
| [sase-1qz.10](sase-1qz.10.md) | Instruct and Edit through the prompt bar | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |
| [sase-1qz.11](sase-1qz.11.md) | Remove the flag, document, and prove it end to end | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |
| [sase-1qz.2](sase-1qz.2.md) | sase-core: escalation policy, continuation prompt, and config | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |
| [sase-1qz.3](sase-1qz.3.md) | Runner settlement that keeps custody | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |
| [sase-1qz.4](sase-1qz.4.md) | The stop protocol and \`sase agent hijack\` | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |
| [sase-1qz.5](sase-1qz.5.md) | Every release path respects a hijack | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |
| [sase-1qz.6](sase-1qz.6.md) | Keep-the-work recovery (Escalate, Switch, Continue, Instruct) | ◐ in_progress | large | 2026-11-02 | 1 | 0 |
| [sase-1qz.7](sase-1qz.7.md) | Start-over and leave recovery (Restart, Edit backend, Dismiss) | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |
| [sase-1qz.8](sase-1qz.8.md) | Agents-tab rendering and the ,k way in | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |
| [sase-1qz.9](sase-1qz.9.md) | The recovery panel | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1qz: Agent Hijack: stop a stalled agent, keep its work, recover in one keypress [in_progress]"]
    n1["sase-1qz.1: sase-core: hijack statuses, ledger wire, and eligibility [closed]"]
    n2["sase-1qz.10: Instruct and Edit through the prompt bar [in_progress]"]
    n3["sase-1qz.11: Remove the flag, document, and prove it end to end [in_progress]"]
    n4["sase-1qz.2: sase-core: escalation policy, continuation prompt, and config [in_progress]"]
    n5["sase-1qz.3: Runner settlement that keeps custody [in_progress]"]
    n6["sase-1qz.4: The stop protocol and `sase agent hijack` [in_progress]"]
    n7["sase-1qz.5: Every release path respects a hijack [in_progress]"]
    n8["sase-1qz.6: Keep-the-work recovery (Escalate, Switch, Continue, Instruct) [in_progress]"]
    n9["sase-1qz.7: Start-over and leave recovery (Restart, Edit backend, Dismiss) [in_progress]"]
    n10["sase-1qz.8: Agents-tab rendering and the ,k way in [in_progress]"]
    n11["sase-1qz.9: The recovery panel [in_progress]"]
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
    n0 --> n11
    n1 -.-> n5
    n2 -.-> n3
    n4 -.-> n8
    n5 -.-> n6
    n6 -.-> n7
    n6 -.-> n10
    n7 -.-> n3
    n7 -.-> n8
    n8 -.-> n9
    n9 -.-> n11
    n10 -.-> n11
    n11 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1qz.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.1/README.md) | [sase-1qz.1](sase-1qz.1.md) | 2 |
| [bbugyi200.apollo.sase-1qz.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.10/README.md) | [sase-1qz.10](sase-1qz.10.md) | 0 |
| [bbugyi200.apollo.sase-1qz.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.11/README.md) | [sase-1qz.11](sase-1qz.11.md) | 0 |
| [bbugyi200.apollo.sase-1qz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1qz.2.md) | [sase-1qz.2](sase-1qz.2.md) | 0 |
| [bbugyi200.apollo.sase-1qz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.3/README.md) | [sase-1qz.3](sase-1qz.3.md) | 0 |
| [bbugyi200.apollo.sase-1qz.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.4/README.md) | [sase-1qz.4](sase-1qz.4.md) | 0 |
| [bbugyi200.apollo.sase-1qz.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.5/README.md) | [sase-1qz.5](sase-1qz.5.md) | 0 |
| [bbugyi200.apollo.sase-1qz.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.6/README.md) | [sase-1qz.6](sase-1qz.6.md) | 0 |
| [bbugyi200.apollo.sase-1qz.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.7/README.md) | [sase-1qz.7](sase-1qz.7.md) | 0 |
| [bbugyi200.apollo.sase-1qz.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.8/README.md) | [sase-1qz.8](sase-1qz.8.md) | 0 |
| [bbugyi200.apollo.sase-1qz.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.9/README.md) | [sase-1qz.9](sase-1qz.9.md) | 0 |
| [bbugyi200.apollo.sase-1qz.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.land/README.md) | [sase-1qz](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@65925ca`](https://github.com/sase-org/sase-core/commit/65925ca8b6427fc0037c9ddbb5ebba8e6927fabe) | feat(agent-hijack): add core ledger and eligibility | [sase-1qz.1](sase-1qz.1.md) | 2026-11-02 20:45:42 EST |
| sase | [`85c8d46`](https://github.com/sase-org/sase/commit/85c8d4613a3a8ef06ec2e67de6c398d59b92b412) | feat(agent-hijack): add Python hijack workflow wrappers | [sase-1qz.1](sase-1qz.1.md) | 2026-11-02 20:48:03 EST |

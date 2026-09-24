# Bead: sase-17m — Rename agent family to sase agent session

[Bead Pages](../README.md) / sase-17m

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qh.md) · **Assignee:** `sase-17m.land`
**Created:** 2026-09-23 22:46:33 EDT
**Plan:** [202609/agent\_session\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_rename.md)

## Description

The concept formerly called an agent family is named a sase agent session (agent session) on every current surface in sase, sase-core, sase-telegram, and chezmoi: code, wire contracts, persisted output, CLI, prompt syntax, ACE, skills, docs, and memory. Pre-rename data still loads, retired user syntax keeps working behind a sunset flag, and unrelated meanings of "family" are unchanged.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-17m.1](sase-17m.1.md) | Free the agent session name | ✓ closed | small | 2026-09-23 | 1 | 1 |
| [sase-17m.10](sase-17m.10.md) | Cross-repo audit, guardrail, and deploy | ◐ in_progress | medium | 2026-09-23 | 1 | 0 |
| [sase-17m.2](sase-17m.2.md) | sase-core additive rename | ✓ closed | large | 2026-09-23 | 1 | 0 |
| [sase-17m.3](sase-17m.3.md) | Python persistence and wire cutover | ◐ in_progress | large | 2026-09-23 | 1 | 0 |
| [sase-17m.4](sase-17m.4.md) | Runtime, syntax, and CLI cutover | ◐ in_progress | large | 2026-09-23 | 1 | 0 |
| [sase-17m.5](sase-17m.5.md) | ACE agent session surfaces | ◐ in_progress | large | 2026-09-23 | 1 | 0 |
| [sase-17m.6](sase-17m.6.md) | Documentation and memory | ◐ in_progress | medium | 2026-09-23 | 1 | 0 |
| [sase-17m.7](sase-17m.7.md) | sase-telegram cutover | ◐ in_progress | small | 2026-09-23 | 1 | 0 |
| [sase-17m.8](sase-17m.8.md) | sase-core contract flip | ◐ in_progress | medium | 2026-09-23 | 1 | 0 |
| [sase-17m.9](sase-17m.9.md) | Pin bump and agents sidecar session pages | ◐ in_progress | medium | 2026-09-23 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-17m: Rename agent family to sase agent session [in_progress]"]
    n1["sase-17m.1: Free the agent session name [closed]"]
    n2["sase-17m.10: Cross-repo audit, guardrail, and deploy [in_progress]"]
    n3["sase-17m.2: sase-core additive rename [closed]"]
    n4["sase-17m.2.1: sase-core additive agent-session rename (core-expand) [closed]"]
    n5["sase-17m.2.1.1: Identity, launch, holds, and directive/editor surfaces [closed]"]
    n6["sase-17m.2.1.2: Scan, runtime, lifecycle, runner, and stats wires [closed]"]
    n7["sase-17m.2.1.3: Fleet core and gateway [closed]"]
    n8["sase-17m.2.1.4: Classification sweep and cross-repo verification [closed]"]
    n9["sase-17m.3: Python persistence and wire cutover [in_progress]"]
    n10["sase-17m.3.1: Python persistence and wire cutover to agent session (wire-cutover) [in_progress]"]
    n11["sase-17m.3.1.1: Core pin bump and new binding names [in_progress]"]
    n12["sase-17m.3.1.2: Canonical agent-session metadata keys and shared accessor [in_progress]"]
    n13["sase-17m.3.1.3: Python wire mirrors hydrate either spelling [in_progress]"]
    n14["sase-17m.3.1.4: Agent model fields [in_progress]"]
    n15["sase-17m.3.1.5: Durable Python-owned JSON surfaces [in_progress]"]
    n16["sase-17m.3.1.6: Agent name registry session kinds and schema v3 [in_progress]"]
    n17["sase-17m.3.1.7: Classification sweep and phase verification [in_progress]"]
    n18["sase-17m.4: Runtime, syntax, and CLI cutover [in_progress]"]
    n19["sase-17m.5: ACE agent session surfaces [in_progress]"]
    n20["sase-17m.6: Documentation and memory [in_progress]"]
    n21["sase-17m.7: sase-telegram cutover [in_progress]"]
    n22["sase-17m.8: sase-core contract flip [in_progress]"]
    n23["sase-17m.9: Pin bump and agents sidecar session pages [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n3 --> n4
    n4 --> n5
    n4 --> n6
    n4 --> n7
    n4 --> n8
    n0 --> n9
    n9 --> n10
    n10 --> n11
    n10 --> n12
    n10 --> n13
    n10 --> n14
    n10 --> n15
    n10 --> n16
    n10 --> n17
    n0 --> n18
    n0 --> n19
    n0 --> n20
    n0 --> n21
    n0 --> n22
    n0 --> n23
    n1 -.-> n9
    n3 -.-> n9
    n5 -.-> n6
    n6 -.-> n7
    n7 -.-> n8
    n9 -.-> n18
    n11 -.-> n12
    n12 -.-> n13
    n13 -.-> n14
    n14 -.-> n15
    n14 -.-> n16
    n15 -.-> n17
    n16 -.-> n17
    n18 -.-> n19
    n18 -.-> n20
    n18 -.-> n21
    n19 -.-> n22
    n20 -.-> n22
    n21 -.-> n22
    n22 -.-> n23
    n23 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.1/README.md) | [sase-17m.1](sase-17m.1.md) | 1 |
| [bbugyi200.athena.sase-17m.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.10/README.md) | [sase-17m.10](sase-17m.10.md) | 0 |
| [bbugyi200.athena.sase-17m.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.2.md) | [sase-17m.2](sase-17m.2.md) | 0 |
| [bbugyi200.athena.sase-17m.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.1/README.md) | [sase-17m.2.1.1](sase-17m.2.1.1.md) | 2 |
| [bbugyi200.athena.sase-17m.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.2/README.md) | [sase-17m.2.1.2](sase-17m.2.1.2.md) | 1 |
| [bbugyi200.athena.sase-17m.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.3/README.md) | [sase-17m.2.1.3](sase-17m.2.1.3.md) | 1 |
| [bbugyi200.athena.sase-17m.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.4/README.md) | [sase-17m.2.1.4](sase-17m.2.1.4.md) | 1 |
| [bbugyi200.athena.sase-17m.2.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.land/README.md) | [sase-17m.2.1](sase-17m.2.1.md) | 1 |
| [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) | [sase-17m.3](sase-17m.3.md) | 0 |
| [bbugyi200.athena.sase-17m.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.1/README.md) | [sase-17m.3.1.1](sase-17m.3.1.1.md) | 0 |
| [bbugyi200.athena.sase-17m.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.2/README.md) | [sase-17m.3.1.2](sase-17m.3.1.2.md) | 0 |
| [bbugyi200.athena.sase-17m.3.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.3/README.md) | [sase-17m.3.1.3](sase-17m.3.1.3.md) | 0 |
| [bbugyi200.athena.sase-17m.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.4/README.md) | [sase-17m.3.1.4](sase-17m.3.1.4.md) | 0 |
| [bbugyi200.athena.sase-17m.3.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.5/README.md) | [sase-17m.3.1.5](sase-17m.3.1.5.md) | 0 |
| [bbugyi200.athena.sase-17m.3.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.6/README.md) | [sase-17m.3.1.6](sase-17m.3.1.6.md) | 0 |
| [bbugyi200.athena.sase-17m.3.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.7/README.md) | [sase-17m.3.1.7](sase-17m.3.1.7.md) | 0 |
| [bbugyi200.athena.sase-17m.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.land/README.md) | [sase-17m.3.1](sase-17m.3.1.md) | 0 |
| [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4/README.md) | [sase-17m.4](sase-17m.4.md) | 0 |
| [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5/README.md) | [sase-17m.5](sase-17m.5.md) | 0 |
| [bbugyi200.athena.sase-17m.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.6/README.md) | [sase-17m.6](sase-17m.6.md) | 0 |
| [bbugyi200.athena.sase-17m.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.7/README.md) | [sase-17m.7](sase-17m.7.md) | 0 |
| [bbugyi200.athena.sase-17m.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.8/README.md) | [sase-17m.8](sase-17m.8.md) | 0 |
| [bbugyi200.athena.sase-17m.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.9/README.md) | [sase-17m.9](sase-17m.9.md) | 0 |
| [bbugyi200.athena.sase-17m.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.land/README.md) | [sase-17m](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e662494`](https://github.com/sase-org/sase/commit/e662494ba5af6af123cf88e026555a87f4476b40) | refactor(free-name): rename transcript resolvers, tmux helpers, and agent-run prose | [sase-17m.1](sase-17m.1.md) | 2026-09-23 23:02:35 EDT |
| sase | [`a764a76`](https://github.com/sase-org/sase/commit/a764a76d41fbcacfe08ecbf93a351d3c53d732ad) | feat(ace): tolerate new agent-session spelling in directive contract and completion | [sase-17m.2.1.1](sase-17m.2.1.1.md) | 2026-09-24 00:05:04 EDT |
| sase-core | [`sase-core@c5b9c0d`](https://github.com/sase-org/sase-core/commit/c5b9c0d68867fb1cef8923b06270e39d5f9533d1) | feat(core): additive agent-session rename for identity, launch, holds, and editor surfaces | [sase-17m.2.1.1](sase-17m.2.1.1.md) | 2026-09-24 00:09:36 EDT |
| sase-core | [`sase-core@ef82848`](https://github.com/sase-org/sase-core/commit/ef8284804ab894ed8f3277726bea1e4cc34a6864) | feat(core): additive agent-session rename for scan, runtime, lifecycle, runner, and stats wires | [sase-17m.2.1.2](sase-17m.2.1.2.md) | 2026-09-24 01:01:58 EDT |
| sase-core | [`sase-core@b814a0f`](https://github.com/sase-org/sase-core/commit/b814a0fc08ad5a94aba5863fa4550b3622ac9126) | refactor(fleet): rename family to agent session with session key acceptance | [sase-17m.2.1.3](sase-17m.2.1.3.md) | 2026-09-24 01:35:09 EDT |
| sase-core | [`sase-core@ae9dbf6`](https://github.com/sase-org/sase-core/commit/ae9dbf6e0719761d825478021aa8ff8d7b27aae8) | refactor(core): sweep remaining agent-family spellings to agent session | [sase-17m.2.1.4](sase-17m.2.1.4.md) | 2026-09-24 02:35:32 EDT |
| sase--plans | [`sase--plans@f4ede6d`](https://github.com/sase-org/sase--plans/commit/f4ede6dd559c0b0bc69003ba9e615f130e3b8c6f) | chore(plans): mark agent\_session\_core\_expand plan done after sase-17m.2.1 landed | [sase-17m.2.1](sase-17m.2.1.md) | 2026-09-24 03:02:21 EDT |

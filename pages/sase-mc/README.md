# Bead: sase-mc — Temporarily Disable LLM Providers

[Bead Pages](../README.md) / sase-mc

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02f.md) · **Assignee:** `sase-mc.land`
**Created:** 2026-08-15 11:11:45 EDT
**Plan:** [202608/temporary\_provider\_disabling.md](https://github.com/sase-org/sase--plans/blob/main/202608/temporary_provider_disabling.md)

## Description

Let users temporarily disable one or more registered LLM providers from the ACE Models panel, with durable machine-wide expiry state, routing semantics that remove disabled providers from alias pools and ordered fallbacks, preserved-but-suspended alias overrides, actionable failures for direct explicit requests, and a polished provider-management/countdown experience that stays responsive and visible.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-mc.1](sase-mc.1.md) | Add the Rust-owned temporary provider-disable state contract | ✓ closed | medium | 2026-08-15 | 1 | 1 |
| [sase-mc.2](sase-mc.2.md) | Make every model-selection path honor disabled providers | ◐ in_progress | medium | 2026-08-15 | 1 | 0 |
| [sase-mc.3](sase-mc.3.md) | Build the Provider Routing experience in the Models panel | ◐ in_progress | medium | 2026-08-15 | 1 | 0 |
| [sase-mc.4](sase-mc.4.md) | Document, stress, and land the combined provider-disable feature | ◐ in_progress | small | 2026-08-15 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-mc: Temporarily Disable LLM Providers [in_progress]"]
    n1["sase-mc.1: Add the Rust-owned temporary provider-disable state contract [closed]"]
    n2["sase-mc.2: Make every model-selection path honor disabled providers [in_progress]"]
    n3["sase-mc.3: Build the Provider Routing experience in the Models panel [in_progress]"]
    n4["sase-mc.4: Document, stress, and land the combined provider-disable feature [in_progress]"]
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
| [bbugyi200.athena.sase-mc.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mc.1/README.md) | [sase-mc.1](sase-mc.1.md) | 1 |
| [bbugyi200.athena.sase-mc.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mc.2/README.md) | [sase-mc.2](sase-mc.2.md) | 0 |
| [bbugyi200.athena.sase-mc.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mc.3/README.md) | [sase-mc.3](sase-mc.3.md) | 0 |
| [bbugyi200.athena.sase-mc.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mc.4/README.md) | [sase-mc.4](sase-mc.4.md) | 0 |
| [bbugyi200.athena.sase-mc.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mc.land/README.md) | [sase-mc](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9939f8f`](https://github.com/sase-org/sase-core/commit/9939f8f28ee3ab9a9c1a90f94f17fc58bd3d7c91) | feat(llm-provider): add provider-disable state store | [sase-mc.1](sase-mc.1.md) | 2026-08-15 12:19:57 EDT |

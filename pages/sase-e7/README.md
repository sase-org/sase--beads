# Bead: sase-e7 — Close the remaining canonical prompt-archive gaps in sase-dh

[Bead Pages](../README.md) / sase-e7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rt](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rt/README.md) · **Assignee:** `sase-e7.land`
**Created:** 2026-08-02 13:28:21 UTC
**Plan:** [202608/finish\_dh\_canonical\_archive.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_dh_canonical_archive.md)

## Description

The agents sidecar is the canonical and only home for prompt Markdown in practice as well as in principle: no supported command can write prompt Markdown into plans, prompt search reads the canonical archive, plan authors can write ordinary body bullets named after header labels, the migration command acts on the caller's own sidecar and publishes what it commits, the shipped docs and directory map match the implementation, and sase-dh is closed on verified evidence.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-e7.1](sase-e7.1.md) | Restrict plan-header parsing to the leading block | ✓ closed | medium | 1 | 1 |
| [sase-e7.2](sase-e7.2.md) | Make every prompt interface canonical | ◐ in_progress | medium | 1 | 0 |
| [sase-e7.3](sase-e7.3.md) | Make agent prompts migrate correct and durable | ◐ in_progress | medium | 1 | 0 |
| [sase-e7.4](sase-e7.4.md) | Correct the directory-map asset and the prompt docs | ◐ in_progress | small | 1 | 0 |
| [sase-e7.5](sase-e7.5.md) | Close out sase-dh | ◐ in_progress | medium | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-e7: Close the remaining canonical prompt-archive gaps in sase-dh [in_progress]"]
    n1["sase-e7.1: Restrict plan-header parsing to the leading block [closed]"]
    n2["sase-e7.2: Make every prompt interface canonical [in_progress]"]
    n3["sase-e7.3: Make agent prompts migrate correct and durable [in_progress]"]
    n4["sase-e7.4: Correct the directory-map asset and the prompt docs [in_progress]"]
    n5["sase-e7.5: Close out sase-dh [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n5
    n2 -.-> n4
    n2 -.-> n5
    n3 -.-> n5
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e7.1/README.md) | [sase-e7.1](sase-e7.1.md) | 1 |
| [bbugyi200.athena.sase-e7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e7.2/README.md) | [sase-e7.2](sase-e7.2.md) | 0 |
| [bbugyi200.athena.sase-e7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e7.3/README.md) | [sase-e7.3](sase-e7.3.md) | 0 |
| [bbugyi200.athena.sase-e7.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e7.4/README.md) | [sase-e7.4](sase-e7.4.md) | 0 |
| [bbugyi200.athena.sase-e7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e7.5/README.md) | [sase-e7.5](sase-e7.5.md) | 0 |
| [bbugyi200.athena.sase-e7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e7.land/README.md) | [sase-e7](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@d7cfed8`](https://github.com/sase-org/sase-core/commit/d7cfed84d5d7ea0584baa326f5c25abaf94a9293) | fix(plan): restrict header parsing to leading block | [sase-e7.1](sase-e7.1.md) | 2026-08-02 13:41:33 |

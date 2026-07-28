# Bead: sase-ak — Validate and display %wait agent-tribe references correctly

[Bead Pages](../README.md) / sase-ak

**Status:** ◎ claimed · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ak.land`
**Created:** 2026-07-28 21:04:51 UTC
**Plan:** [202607/tribe\_wait\_reference\_validation\_and\_display.md](https://github.com/sase-org/sase--plans/blob/main/202607/tribe_wait_reference_validation_and_display.md)

## Description

A `%wait(@<tribe>)` target is understood end to end: reserved pseudo-tribe references such as `@default` are rejected at launch instead of parking an agent forever, and the ACE Agents tab renders a real tribe wait as a pending-or-bound tribe target instead of a missing agent name.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-ak.1](sase-ak.1.md) | Reject reserved tribe references in wait and fork targets | ✓ closed | small | 1 | 1 |
| [sase-ak.2](sase-ak.2.md) | Shared tribe wait binding resolver | ◐ in_progress | medium | 1 | 0 |
| [sase-ak.3](sase-ak.3.md) | Tribe-aware wait rendering in the Agents tab | ◎ claimed | medium | 1 | 0 |
| [sase-ak.4](sase-ak.4.md) | Surface waits that can never resolve | ◎ claimed | small | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ak: Validate and display %wait agent-tribe references correctly [claimed]"]
    n1["sase-ak.1: Reject reserved tribe references in wait and fork targets [closed]"]
    n2["sase-ak.2: Shared tribe wait binding resolver [in_progress]"]
    n3["sase-ak.3: Tribe-aware wait rendering in the Agents tab [claimed]"]
    n4["sase-ak.4: Surface waits that can never resolve [claimed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n4
    n2 -.-> n3
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ak.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ak.1/README.md) | [sase-ak.1](sase-ak.1.md) | 1 |
| [bbugyi200.athena.sase-ak.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ak.2/README.md) | [sase-ak.2](sase-ak.2.md) | 0 |
| [bbugyi200.athena.sase-ak.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ak.3/README.md) | [sase-ak.3](sase-ak.3.md) | 0 |
| [bbugyi200.athena.sase-ak.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ak.4/README.md) | [sase-ak.4](sase-ak.4.md) | 0 |
| [bbugyi200.athena.sase-ak.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ak.land/README.md) | [sase-ak](README.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`d67de4c`](https://github.com/sase-org/sase/commit/d67de4caf9530ff1a4912ffa4ecf2727a50d35df) | fix(tribes): reject reserved tribe references in wait and fork targets | [sase-ak.1](sase-ak.1.md) | 2026-07-28 21:17:58 |

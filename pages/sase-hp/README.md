# Bead: sase-hp — XPrompt target mode for the prompt input stack

[Bead Pages](../README.md) / sase-hp

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vy/README.md) · **Assignee:** `sase-hp.land`
**Created:** 2026-08-08 15:51:55 EDT
**Plan:** [202608/xprompt\_target\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_target_mode.md)

## Description

Editing an existing xprompt definition from the ACE TUI is a first-class, obvious, reliable loop: loading a definition from any surface puts the prompt input widget stack into a visibly distinct "targeting" state, <enter> offers a single-keypress "save to the targeted xprompt" option, and saving writes the correct file (chezmoi source included) and then offers exactly the follow-up actions that file needs — commit/push, a scoped chezmoi apply, or the matching `sase memory init` / `sase skill init`.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-hp.1](sase-hp.1.md) | Targeting model, reference identity, and chezmoi-aware write paths | ✓ closed | medium | 2026-08-08 | 1 | 1 |
| [sase-hp.2](sase-hp.2.md) | Every definition-load surface targets its xprompt | ◐ in_progress | medium | 2026-08-08 | 1 | 0 |
| [sase-hp.3](sase-hp.3.md) | Target-aware \<enter\> chooser with a single-key save | ✓ closed | medium | 2026-08-08 | 1 | 1 |
| [sase-hp.4](sase-hp.4.md) | Post-write follow-up actions with memory and skill init integration | ◐ in_progress | medium | 2026-08-08 | 1 | 0 |
| [sase-hp.5](sase-hp.5.md) | Visual language for the targeting state | ◐ in_progress | medium | 2026-08-08 | 1 | 0 |
| [sase-hp.6](sase-hp.6.md) | Help modal, footer, and documentation | ◐ in_progress | small | 2026-08-08 | 1 | 0 |
| [sase-hp.7](sase-hp.7.md) | End-to-end verification of the edit loop | ◐ in_progress | small | 2026-08-08 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-hp: XPrompt target mode for the prompt input stack [in_progress]"]
    n1["sase-hp.1: Targeting model, reference identity, and chezmoi-aware write paths [closed]"]
    n2["sase-hp.2: Every definition-load surface targets its xprompt [in_progress]"]
    n3["sase-hp.3: Target-aware &lt;enter&gt; chooser with a single-key save [closed]"]
    n4["sase-hp.4: Post-write follow-up actions with memory and skill init integration [in_progress]"]
    n5["sase-hp.5: Visual language for the targeting state [in_progress]"]
    n6["sase-hp.6: Help modal, footer, and documentation [in_progress]"]
    n7["sase-hp.7: End-to-end verification of the edit loop [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n2
    n1 -.-> n3
    n1 -.-> n4
    n1 -.-> n5
    n2 -.-> n6
    n3 -.-> n5
    n3 -.-> n6
    n4 -.-> n6
    n5 -.-> n6
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hp.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hp.1/README.md) | [sase-hp.1](sase-hp.1.md) | 1 |
| [bbugyi200.athena.sase-hp.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hp.2/README.md) | [sase-hp.2](sase-hp.2.md) | 0 |
| [bbugyi200.athena.sase-hp.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hp.3/README.md) | [sase-hp.3](sase-hp.3.md) | 1 |
| [bbugyi200.athena.sase-hp.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hp.4/README.md) | [sase-hp.4](sase-hp.4.md) | 0 |
| [bbugyi200.athena.sase-hp.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hp.5/README.md) | [sase-hp.5](sase-hp.5.md) | 0 |
| [bbugyi200.athena.sase-hp.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hp.6/README.md) | [sase-hp.6](sase-hp.6.md) | 0 |
| [bbugyi200.athena.sase-hp.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hp.7/README.md) | [sase-hp.7](sase-hp.7.md) | 0 |
| [bbugyi200.athena.sase-hp.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hp.land/README.md) | [sase-hp](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7a9a56b`](https://github.com/sase-org/sase/commit/7a9a56b85caefc1c8c15931918e69d0af2511ece) | feat: route xprompt edits through write targets | [sase-hp.1](sase-hp.1.md) | 2026-08-08 16:19:51 EDT |
| sase | [`48e8f10`](https://github.com/sase-org/sase/commit/48e8f10d3c792e027750318533a5518c94df4260) | feat(tui): add target-aware prompt submit chooser | [sase-hp.3](sase-hp.3.md) | 2026-08-08 17:05:16 EDT |

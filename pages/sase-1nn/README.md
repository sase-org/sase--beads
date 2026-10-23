# Bead: sase-1nn — Green master's release gates and ship sase v0.18.1 to PyPI through ci\_watch

[Bead Pages](../README.md) / sase-1nn

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.137](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.137.md) · **Assignee:** `sase-1nn.land`
**Created:** 2026-10-23 11:30:05 EDT
**Plan:** [202610/v0\_18\_1\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release.md)

## Description

Master Gate is green at master HEAD, a fresh Full CI run on master is green, ci_watch merges the release-please PR for 0.18.1, Publish uploads sase 0.18.1 to PyPI, a clean install of it works, and the final lander records that evidence as an artifact.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1nn.1](sase-1nn.1.md) | Repair sase-core's release-plz merge filter | ✓ closed | small | 2026-10-23 | 1 | 1 |
| [sase-1nn.2](sase-1nn.2.md) | Cut sase-core-rs 0.42.2 and raise sase's exact core pin | ◐ in_progress | medium | 2026-10-23 | 1 | 0 |
| [sase-1nn.3](sase-1nn.3.md) | Restore Full CI's build-core job and authenticate release metadata sync | ◎ claimed | small | 2026-10-23 | 1 | 0 |
| [sase-1nn.4](sase-1nn.4.md) | Make the custom gate modal sizing tests deterministic | ◐ in_progress | small | 2026-10-23 | 1 | 0 |
| [sase-1nn.5](sase-1nn.5.md) | Make the visual screenshot check clean on UTC runners | ◐ in_progress | medium | 2026-10-23 | 1 | 0 |
| [sase-1nn.6](sase-1nn.6.md) | Run Full CI on the repaired tip and fix every other red | ◐ in_progress | medium | 2026-10-23 | 1 | 0 |
| [sase-1nn.7](sase-1nn.7.md) | Watch v0.18.1 through ci\_watch, Publish, and PyPI with a self-closing monitor | ◐ in_progress | small | 2026-10-23 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1nn: Green master's release gates and ship sase v0.18.1 to PyPI through ci_watch [in_progress]"]
    n1["sase-1nn.1: Repair sase-core's release-plz merge filter [closed]"]
    n2["sase-1nn.2: Cut sase-core-rs 0.42.2 and raise sase's exact core pin [in_progress]"]
    n3["sase-1nn.3: Restore Full CI's build-core job and authenticate release metadata sync [claimed]"]
    n4["sase-1nn.4: Make the custom gate modal sizing tests deterministic [in_progress]"]
    n5["sase-1nn.5: Make the visual screenshot check clean on UTC runners [in_progress]"]
    n6["sase-1nn.6: Run Full CI on the repaired tip and fix every other red [in_progress]"]
    n7["sase-1nn.7: Watch v0.18.1 through ci_watch, Publish, and PyPI with a self-closing monitor [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n2
    n2 -.-> n7
    n3 -.-> n6
    n3 -.-> n7
    n4 -.-> n5
    n4 -.-> n7
    n5 -.-> n7
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.1/README.md) | [sase-1nn.1](sase-1nn.1.md) | 1 |
| [bbugyi200.athena.sase-1nn.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.2/README.md) | [sase-1nn.2](sase-1nn.2.md) | 0 |
| [bbugyi200.athena.sase-1nn.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.3.md) | [sase-1nn.3](sase-1nn.3.md) | 0 |
| [bbugyi200.athena.sase-1nn.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.4/README.md) | [sase-1nn.4](sase-1nn.4.md) | 0 |
| [bbugyi200.athena.sase-1nn.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.5/README.md) | [sase-1nn.5](sase-1nn.5.md) | 0 |
| [bbugyi200.athena.sase-1nn.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.6/README.md) | [sase-1nn.6](sase-1nn.6.md) | 0 |
| [bbugyi200.athena.sase-1nn.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.7/README.md) | [sase-1nn.7](sase-1nn.7.md) | 0 |
| [bbugyi200.athena.sase-1nn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.land/README.md) | [sase-1nn](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@db2ce63`](https://github.com/sase-org/sase-core/commit/db2ce6375a7bb92c7218d6190f2a6346952e6ad5) | fix(release): make release-plz PR filter jq-safe | [sase-1nn.1](sase-1nn.1.md) | 2026-10-23 11:55:15 EDT |

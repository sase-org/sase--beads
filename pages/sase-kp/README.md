# Bead: sase-kp — sase monitor — long-running commands as first-class agent family members

[Bead Pages](../README.md) / sase-kp

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yy/README.md) · **Assignee:** `sase-kp.land`
**Created:** 2026-08-12 17:27:55 EDT
**Plan:** [202608/sase\_monitor.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_monitor.md)

## Description

Agents can hand a slow command (`just check-full`, a CI wait, `sase bead work`) to `sase monitor start` and be killed cleanly, while the command keeps running as a live, first-class monitor member of their agent family — with streaming output, live runtime, custom start/stop statuses, a timeout, and an optional follow-up agent that resumes the same workspace and conversation when the command finishes.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-kp.1](sase-kp.1.md) | Monitor marker fields on the agent scan wire | ✓ closed | small | 2026-08-12 | 1 | 2 |
| [sase-kp.10](sase-kp.10.md) | /sase\_monitor skill | ◐ in_progress | small | 2026-08-12 | 1 | 0 |
| [sase-kp.11](sase-kp.11.md) | Memory and documentation updates | ◐ in_progress | small | 2026-08-12 | 1 | 0 |
| [sase-kp.12](sase-kp.12.md) | End-to-end monitor exercises | ◐ in_progress | xsmall | 2026-08-12 | 1 | 0 |
| [sase-kp.2](sase-kp.2.md) | First-class custom agent status labels | ✓ closed | medium | 2026-08-12 | 1 | 1 |
| [sase-kp.3](sase-kp.3.md) | Monitor member lifecycle and supervisor process | ✓ closed | medium | 2026-08-12 | 1 | 1 |
| [sase-kp.4](sase-kp.4.md) | Follow-up agent handoff after a monitor completes | ◐ in_progress | medium | 2026-08-12 | 1 | 0 |
| [sase-kp.5](sase-kp.5.md) | In-agent handoff marker and runner adoption | ◐ in_progress | medium | 2026-08-12 | 1 | 0 |
| [sase-kp.6](sase-kp.6.md) | sase monitor command group | ◐ in_progress | medium | 2026-08-12 | 1 | 0 |
| [sase-kp.7](sase-kp.7.md) | Monitor rows in agent lists and family rosters | ◐ in_progress | medium | 2026-08-12 | 1 | 0 |
| [sase-kp.8](sase-kp.8.md) | Monitor detail panel, live output, and keybindings | ◐ in_progress | medium | 2026-08-12 | 1 | 0 |
| [sase-kp.9](sase-kp.9.md) | Approved-epic launch runs as a monitor | ◐ in_progress | medium | 2026-08-12 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-kp: sase monitor — long-running commands as first-class agent family members [in_progress]"]
    n1["sase-kp.1: Monitor marker fields on the agent scan wire [closed]"]
    n2["sase-kp.10: /sase_monitor skill [in_progress]"]
    n3["sase-kp.11: Memory and documentation updates [in_progress]"]
    n4["sase-kp.12: End-to-end monitor exercises [in_progress]"]
    n5["sase-kp.2: First-class custom agent status labels [closed]"]
    n6["sase-kp.3: Monitor member lifecycle and supervisor process [closed]"]
    n7["sase-kp.4: Follow-up agent handoff after a monitor completes [in_progress]"]
    n8["sase-kp.5: In-agent handoff marker and runner adoption [in_progress]"]
    n9["sase-kp.6: sase monitor command group [in_progress]"]
    n10["sase-kp.7: Monitor rows in agent lists and family rosters [in_progress]"]
    n11["sase-kp.8: Monitor detail panel, live output, and keybindings [in_progress]"]
    n12["sase-kp.9: Approved-epic launch runs as a monitor [in_progress]"]
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
    n0 --> n12
    n1 -.-> n6
    n2 -.-> n3
    n3 -.-> n4
    n5 -.-> n6
    n5 -.-> n10
    n6 -.-> n7
    n6 -.-> n8
    n6 -.-> n10
    n7 -.-> n9
    n8 -.-> n9
    n9 -.-> n2
    n9 -.-> n11
    n9 -.-> n12
    n10 -.-> n11
    n11 -.-> n4
    n12 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kp.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.1/README.md) | [sase-kp.1](sase-kp.1.md) | 2 |
| [bbugyi200.athena.sase-kp.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.10/README.md) | [sase-kp.10](sase-kp.10.md) | 0 |
| [bbugyi200.athena.sase-kp.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.11/README.md) | [sase-kp.11](sase-kp.11.md) | 0 |
| [bbugyi200.athena.sase-kp.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.12/README.md) | [sase-kp.12](sase-kp.12.md) | 0 |
| [bbugyi200.athena.sase-kp.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.2/README.md) | [sase-kp.2](sase-kp.2.md) | 1 |
| [bbugyi200.athena.sase-kp.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.3/README.md) | [sase-kp.3](sase-kp.3.md) | 1 |
| [bbugyi200.athena.sase-kp.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.4/README.md) | [sase-kp.4](sase-kp.4.md) | 0 |
| [bbugyi200.athena.sase-kp.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.5/README.md) | [sase-kp.5](sase-kp.5.md) | 0 |
| [bbugyi200.athena.sase-kp.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.6/README.md) | [sase-kp.6](sase-kp.6.md) | 0 |
| [bbugyi200.athena.sase-kp.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.7/README.md) | [sase-kp.7](sase-kp.7.md) | 0 |
| [bbugyi200.athena.sase-kp.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.8/README.md) | [sase-kp.8](sase-kp.8.md) | 0 |
| [bbugyi200.athena.sase-kp.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.9/README.md) | [sase-kp.9](sase-kp.9.md) | 0 |
| [bbugyi200.athena.sase-kp.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.land/README.md) | [sase-kp](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cb91149`](https://github.com/sase-org/sase-core/commit/cb91149efa64a9ba0c342ac8b7e3ba0d5e650b10) | feat(agent-scan): add monitor marker fields to the agent scan wire | [sase-kp.1](sase-kp.1.md) | 2026-08-12 17:45:57 EDT |
| sase | [`3c37f8e`](https://github.com/sase-org/sase/commit/3c37f8e3651bae1f0b53b759efdafffa86a5e2fd) | feat(agent-scan): mirror monitor marker fields on the Python wire | [sase-kp.1](sase-kp.1.md) | 2026-08-12 18:03:25 EDT |
| sase | [`9bfdaed`](https://github.com/sase-org/sase/commit/9bfdaedd4561b38e8522f716ac4e11c19cdf5d13) | feat(agent): honor custom status bucket overrides | [sase-kp.2](sase-kp.2.md) | 2026-08-12 18:15:00 EDT |
| sase | [`b32167c`](https://github.com/sase-org/sase/commit/b32167c31bca2e28d6dfbd6e8cd5dd86a07a883f) | feat(monitor): add monitor member lifecycle and supervisor process | [sase-kp.3](sase-kp.3.md) | 2026-08-12 19:21:48 EDT |

# Bead: sase-185 — Release the prompt bar at submit via detached pending launches

[Bead Pages](../README.md) / sase-185

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0r6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0r6.md) · **Assignee:** `sase-185.land`
**Created:** 2026-09-24 15:03:15 EDT
**Plan:** [202609/detached\_prompt\_submit.md](https://github.com/sase-org/sase--plans/blob/main/202609/detached_prompt_submit.md)

## Description

Submitting from the ACE prompt input bar removes the bar on the very next paint in every launch flow. Kill/dismiss cleanup waits, provider/hold/dispatch preflights, and launch bookkeeping continue as a visible, cancellable pending launch that hands off to the durable `sase run` proc, and every abort path gives the prompt back.

## Notes

[2026-09-24T20:30:04Z · 0rd] DISCOVERED ISSUE (2026-09-24, master cae16be3c, found while landing an unrelated finalizer close_policy change; reproduced identically with that diff stashed): just check fails at lint (mypy) partly because of this epic. src/sase/ace/tui/actions/agent_workflow/_launch_prompt_inputs.py:178 calls self._accept_resolved_launch(...) but LaunchPromptInputMixin declares no such attribute ([attr-defined]); the method is defined on a different mixin in _launch_submission.py:68. Introduced by 93d8d4140 (sase-185.2, detach accepted agent launch guards). The other 15 mypy errors on master belong to already-noted owners: 5 command_line errors on sase-17x (sase-17p.land note) and 10 agent_detail mixin errors on sase-17d.10.1 / sase-17m.4.1.2. Fix by declaring the method on LaunchPromptInputMixin (TYPE_CHECKING stub or shared protocol), matching how sibling mixins declare host methods.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-185.1](sase-185.1.md) | Pending launch lifecycle and detached relaunch waits | ✓ closed | medium | 2026-09-24 | 1 | 1 |
| [sase-185.2](sase-185.2.md) | Hold and provider guards run after the bar unmounts | ✓ closed | medium | 2026-09-24 | 1 | 1 |
| [sase-185.3](sase-185.3.md) | Dispatch source preflight becomes a pending-launch stage | ✓ closed | small | 2026-09-24 | 1 | 1 |
| [sase-185.4](sase-185.4.md) | Prompt keystroke paths stop loading the project-tag catalog | ✓ closed | small | 2026-09-24 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-185: Release the prompt bar at submit via detached pending launches [in_progress]"]
    n1["sase-185.1: Pending launch lifecycle and detached relaunch waits [closed]"]
    n2["sase-185.2: Hold and provider guards run after the bar unmounts [closed]"]
    n3["sase-185.3: Dispatch source preflight becomes a pending-launch stage [closed]"]
    n4["sase-185.4: Prompt keystroke paths stop loading the project-tag catalog [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n2
    n2 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-185.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.1/README.md) | [sase-185.1](sase-185.1.md) | 1 |
| [bbugyi200.athena.sase-185.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-185.2.md) | [sase-185.2](sase-185.2.md) | 1 |
| [bbugyi200.athena.sase-185.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.3/README.md) | [sase-185.3](sase-185.3.md) | 1 |
| [bbugyi200.athena.sase-185.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.4/README.md) | [sase-185.4](sase-185.4.md) | 1 |
| [bbugyi200.athena.sase-185.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.land/README.md) | [sase-185](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`02dd052`](https://github.com/sase-org/sase/commit/02dd0527f903203cfdb5e0fad18b0c2049068e07) | feat(ace-tui): keystroke paths use snapshot-only project-tag helpers phase sase-185.4 | [sase-185.4](sase-185.4.md) | 2026-09-24 15:30:38 EDT |
| sase | [`8c4f3f8`](https://github.com/sase-org/sase/commit/8c4f3f8094b9c8c968382ac4ce79e9d5cd788822) | feat(ace): accept prompt submits as pending launches (sase-185.1) | [sase-185.1](sase-185.1.md) | 2026-09-24 15:58:18 EDT |
| sase | [`93d8d41`](https://github.com/sase-org/sase/commit/93d8d4140cea62629942839fa9eee8c962fcf5a0) | feat(ace): detach accepted agent launch guards | [sase-185.2](sase-185.2.md) | 2026-09-24 16:17:44 EDT |
| sase | [`a21985b`](https://github.com/sase-org/sase/commit/a21985b88fe2de892bb221d3a5ab4fa1cec285b7) | feat(ace): detach dispatch source preflight (sase-185.3) | [sase-185.3](sase-185.3.md) | 2026-09-24 16:44:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0rd][1] | Need my note's ordinal to correct an error count | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.0rd/README.md

<!-- sase:referenced-by:end -->

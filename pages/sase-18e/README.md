# Bead: sase-18e — Stop Codex monitor handoffs from being silently cut off

[Bead Pages](../README.md) / sase-18e

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0re](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0re.md) · **Assignee:** `sase-18e.land`
**Created:** 2026-09-24 16:48:53 EDT
**Plan:** [202609/codex\_monitor\_handoff\_cutoff.md](https://github.com/sase-org/sase--plans/blob/main/202609/codex_monitor_handoff_cutoff.md)

## Description

An agent's in-agent handoff (above all `sase monitor start`) either completes or fails loudly. Codex turns can no longer end while a handoff command is still running, monitor starts are fast and never silent, and a killed handoff is recorded and surfaced instead of leaving an assigned bead stuck in_progress.

## Notes

[2026-09-24T23:25:59Z · sase-18e.land] LAND AUDIT (2026-09-24): Reviewed all three closed phase beads, their notes, plan:202609/codex_monitor_handoff_cutoff.md, and phase commits 6a9bac885/c9da1f164/db337969b against current source. Remaining epic work: phase sase-18e.2's core pin is 6d0d0e6, before committed/remote sase-core AgentSession filter 20ac645; the lane-index test still conditionally skips. Proposed a small tale for the pin and removal of that skip. Follow-up triage for resumed land agent: phase .1 note #1, .2 note #3, and .3 notes #1/#3 are the same clean-master mypy/Symvision/test failures already recorded on active epic sase-18f; commit 114fbca89 fixed the lint subset and sase-18f owns the rest. Phase .2 note #2 (speed up explicit -a monitor starts) and .3 note #2 (extend in-flight markers to other handoff CLI commands) are out-of-scope capability expansions, not defects caused by this epic; searched task beads and found no matching active task, and the feature task catalog refuses agent-created feature beads, so retain the source phase notes without creating misclassified bug tasks. Phase .2 note #1 remains epic work in the new tale. Later commits through 33e41c72e were reviewed for overlap; adjacent changes to monitor naming, Codex lint, and process cleanup do not conflict. No --epic-symbol entries remain. Recheck all this and include every outcome in the final close note after the child lands.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-18e.1](sase-18e.1.md) | Codex adapter conformance for handoff commands | ✓ closed | medium | 2026-09-24 | 1 | 1 |
| [sase-18e.2](sase-18e.2.md) | Make in-agent sase monitor start fast and never silent | ✓ closed | medium | 2026-09-24 | 1 | 2 |
| [sase-18e.3](sase-18e.3.md) | Host records and surfaces a killed handoff | ✓ closed | medium | 2026-09-24 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-18e: Stop Codex monitor handoffs from being silently cut off [in_progress]"]
    n1["sase-18e.1: Codex adapter conformance for handoff commands [closed]"]
    n2["sase-18e.2: Make in-agent sase monitor start fast and never silent [closed]"]
    n3["sase-18e.3: Host records and surfaces a killed handoff [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n2 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18e.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18e.1/README.md) | [sase-18e.1](sase-18e.1.md) | 1 |
| [bbugyi200.athena.sase-18e.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18e.2/README.md) | [sase-18e.2](sase-18e.2.md) | 2 |
| [bbugyi200.athena.sase-18e.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18e.3/README.md) | [sase-18e.3](sase-18e.3.md) | 1 |
| [bbugyi200.athena.sase-18e.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-18e.land.md) | [sase-18e](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6a9bac8`](https://github.com/sase-org/sase/commit/6a9bac885fb61920d213dabe246f0b06352428b7) | fix(codex): recover stranded handoff commands | [sase-18e.1](sase-18e.1.md) | 2026-09-24 17:10:33 EDT |
| sase | [`c9da1f1`](https://github.com/sase-org/sase/commit/c9da1f164786b5a94700124bbfb33d806f133b67) | feat(monitor): make in-agent sase monitor start fast and never silent (sase-18e.2) | [sase-18e.2](sase-18e.2.md) | 2026-09-24 18:11:04 EDT |
| sase-core | [`sase-core@20ac645`](https://github.com/sase-org/sase-core/commit/20ac645a754167048b95f2edc9b0c6578ee5f290) | feat(agent-scan): agent\_session candidate filter for the artifact index (sase-18e.2) | [sase-18e.2](sase-18e.2.md) | 2026-09-24 18:16:15 EDT |
| sase | [`db33796`](https://github.com/sase-org/sase/commit/db337969b904f1ef1814090d68d328c8b8d99daa) | feat(monitor): record and surface killed handoffs (sase-18e.3) | [sase-18e.3](sase-18e.3.md) | 2026-09-24 18:49:19 EDT |
| sase | [`4fb83bb`](https://github.com/sase-org/sase/commit/4fb83bb4faa269b8e43db21695879c34072c77de) | feat(monitor): pin sase-core past agent\_session filter and fix symvision survivors | [sase-18e](README.md) | 2026-09-24 20:24:59 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18e.3][1] | epic context | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18e.3/README.md

<!-- sase:referenced-by:end -->

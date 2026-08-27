# Bead: sase-um — Release gate liveness — a fast per-SHA master gate, a scheduled heavy lane, and a ci\_watch allowlist

[Bead Pages](../README.md) / sase-um

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ek](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ek.md) · **Assignee:** `sase-um.land`
**Created:** 2026-08-26 19:12:23 EDT
**Plan:** [202608/release\_gate\_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_liveness.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202608/release_gate_liveness.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_liveness.md

<!-- sase:links:end -->

## Description

sase-org/sase ships releases again without slowing agent velocity: every master commit gets its own uncancelled CI run, the release gate reads only the fast per-SHA gate, the exhaustive suite still runs on a cadence and still guards the release, and ci_watch merges the release PR with the merge strategy the repository actually allows.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-um.1](sase-um.1.md) | Fast per-SHA master gate | ✓ closed | large | 2026-08-26 | 1 | 1 |
| [sase-um.2](sase-um.2.md) | ci\_watch gating allowlist, heavy-lane freshness, and merge strategy | ✓ closed | large | 2026-08-26 | 1 | 0 |
| [sase-um.3](sase-um.3.md) | Scheduled heavy lane off the push path | ✓ closed | medium | 2026-08-26 | 1 | 1 |
| [sase-um.4](sase-um.4.md) | Throttle release-please to a schedule | ✓ closed | medium | 2026-08-26 | 1 | 1 |
| [sase-um.5](sase-um.5.md) | Drive the master gate green | ◐ in_progress | large | 2026-08-26 | 1 | 0 |
| [sase-um.6](sase-um.6.md) | Pin the Rust core revision CI builds | ✓ closed | medium | 2026-08-26 | 1 | 1 |
| [sase-um.7](sase-um.7.md) | Chop configuration rollout | ✓ closed | small | 2026-08-26 | 1 | 0 |
| [sase-um.8](sase-um.8.md) | Measure the acceptance criteria and ship v0.17.0 | ◐ in_progress | small | 2026-08-26 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-um: Release gate liveness — a fast per-SHA master gate, a scheduled heavy lane, and a ci_watch allowlist [in_progress]"]
    n1["sase-um.1: Fast per-SHA master gate [closed]"]
    n2["sase-um.2: ci_watch gating allowlist, heavy-lane freshness, and merge strategy [closed]"]
    n3["sase-um.3: Scheduled heavy lane off the push path [closed]"]
    n4["sase-um.4: Throttle release-please to a schedule [closed]"]
    n5["sase-um.5: Drive the master gate green [in_progress]"]
    n6["sase-um.5.1: Drive the master gate green — fix the fast-suite failures it attributes and realign the drifted visual lane [in_progress]"]
    n7["sase-um.5.1.1: Fix the three fast-suite failures the gate reports [closed]"]
    n8["sase-um.5.1.2: Realign the ACE visual lane with the shipped Artifacts and Link Rail UI [closed]"]
    n9["sase-um.5.1.3: Land, sample the gate on the tip, and record the flakes [in_progress]"]
    n10["sase-um.6: Pin the Rust core revision CI builds [closed]"]
    n11["sase-um.7: Chop configuration rollout [closed]"]
    n12["sase-um.8: Measure the acceptance criteria and ship v0.17.0 [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n5 --> n6
    n6 --> n7
    n6 --> n8
    n6 --> n9
    n0 --> n10
    n0 --> n11
    n0 --> n12
    n1 -.-> n3
    n1 -.-> n5
    n1 -.-> n10
    n1 -.-> n11
    n2 -.-> n11
    n3 -.-> n10
    n3 -.-> n11
    n4 -.-> n12
    n5 -.-> n12
    n7 -.-> n9
    n8 -.-> n9
    n10 -.-> n12
    n11 -.-> n12
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.1.md) | [sase-um.1](sase-um.1.md) | 1 |
| [bbugyi200.athena.sase-um.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.2.md) | [sase-um.2](sase-um.2.md) | 0 |
| [bbugyi200.athena.sase-um.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.3/README.md) | [sase-um.3](sase-um.3.md) | 1 |
| [bbugyi200.athena.sase-um.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.4/README.md) | [sase-um.4](sase-um.4.md) | 1 |
| [bbugyi200.athena.sase-um.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.5.md) | [sase-um.5](sase-um.5.md) | 0 |
| [bbugyi200.athena.sase-um.5.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.5.1.1/README.md) | [sase-um.5.1.1](sase-um.5.1.1.md) | 1 |
| [bbugyi200.athena.sase-um.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.5.1.2/README.md) | [sase-um.5.1.2](sase-um.5.1.2.md) | 1 |
| [bbugyi200.athena.sase-um.5.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.5.1.3/README.md) | [sase-um.5.1.3](sase-um.5.1.3.md) | 2 |
| [bbugyi200.athena.sase-um.5.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.5.1.land/README.md) | [sase-um.5.1](sase-um.5.1.md) | 0 |
| [bbugyi200.athena.sase-um.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.6/README.md) | [sase-um.6](sase-um.6.md) | 1 |
| [bbugyi200.athena.sase-um.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.7/README.md) | [sase-um.7](sase-um.7.md) | 0 |
| [bbugyi200.athena.sase-um.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.8/README.md) | [sase-um.8](sase-um.8.md) | 0 |
| [bbugyi200.athena.sase-um.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.land/README.md) | [sase-um](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bee0592`](https://github.com/sase-org/sase/commit/bee05929dd7104804fd9d13252da1789fcd6e2bb) | ci(release): throttle release-please workflow | [sase-um.4](sase-um.4.md) | 2026-08-26 19:49:15 EDT |
| sase | [`5d8872f`](https://github.com/sase-org/sase/commit/5d8872f4d2ed263d38a41bcedea44fd15e7ba206) | feat(ci): add fast per-SHA master gate with sharded test matrix | [sase-um.1](sase-um.1.md) | 2026-08-27 07:51:23 EDT |
| sase | [`840dd3e`](https://github.com/sase-org/sase/commit/840dd3eb4af4c5c93f4806ef00b31fad3ce02758) | ci: move exhaustive workflow to scheduled full lane | [sase-um.3](sase-um.3.md) | 2026-08-27 08:29:47 EDT |
| sase | [`30f3843`](https://github.com/sase-org/sase/commit/30f384324343eb9f2a6f6a84488276c464532ddb) | fix(fastlane): repair master gate fast-suite failures | [sase-um.5.1.1](sase-um.5.1.1.md) | 2026-08-27 08:43:37 EDT |
| sase | [`eaf4ea8`](https://github.com/sase-org/sase/commit/eaf4ea8919058d4ae5494b56be8007d128b70b26) | test(ace-tui-visual): route Artifacts digit presses through the live seam and rebaseline PNG goldens | [sase-um.5.1.2](sase-um.5.1.2.md) | 2026-08-27 09:11:16 EDT |
| sase | [`a8e72ce`](https://github.com/sase-org/sase/commit/a8e72cebeb234ff9a7c69483bc4ee800fd6e5ec8) | feat(ci): pin the sase-core revision CI builds from | [sase-um.6](sase-um.6.md) | 2026-08-27 09:41:48 EDT |
| sase | [`95444f8`](https://github.com/sase-org/sase/commit/95444f8685283a0635310688a7fa0906d5f4b709) | test(suite-gate): clear parent shard for scaled children | [sase-um.5.1.3](sase-um.5.1.3.md) | 2026-08-27 11:03:54 EDT |
| sase | [`612cabf`](https://github.com/sase-org/sase/commit/612cabf85a786d9bd2beedbb6556788f6869e70e) | fix(agent): carry process identity through scan liveness | [sase-um.5.1.3](sase-um.5.1.3.md) | 2026-08-27 12:52:13 EDT |

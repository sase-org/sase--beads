# Bead: sase-1rq — Repair red GitHub Actions CI across five projects

[Bead Pages](../README.md) / sase-1rq

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19h.md) · **Assignee:** `sase-1rq.land`
**Created:** 2026-11-07 07:46:42 EST
**Plan:** [202611/red\_ci\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202611/red_ci_repair.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/red_ci_repair.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/red_ci_repair.md

<!-- sase:links:end -->

## Description

Every project whose GitHub Actions CI went red in the ~12 hours before 2026-11-07 07:30 EST (sase-core, sase, bob-cli, bob-mac-capture, dotfiles) is green at its default-branch tip, with machine-readable green evidence attached to the phase's final turn, or, after a very large and well-documented effort, carries a research-sidecar report that tells Bryan exactly what is still needed to finish.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1rq.1](sase-1rq.1.md) | Turn sase-core CI green and unblock its release | ✓ closed | xlarge | 2026-11-07 | 1 | 0 |
| [sase-1rq.2](sase-1rq.2.md) | Turn every red sase workflow green | ◐ in_progress | xlarge | 2026-11-07 | 1 | 0 |
| [sase-1rq.3](sase-1rq.3.md) | Turn bob-cli CI green | ◐ in_progress | xlarge | 2026-11-07 | 1 | 0 |
| [sase-1rq.4](sase-1rq.4.md) | Turn bob-mac-capture CI green | ◐ in_progress | xlarge | 2026-11-07 | 1 | 0 |
| [sase-1rq.5](sase-1rq.5.md) | Turn dotfiles CI green | ✓ closed | xlarge | 2026-11-07 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1rq: Repair red GitHub Actions CI across five projects [in_progress]"]
    n1["sase-1rq.1: Turn sase-core CI green and unblock its release [closed]"]
    n2["sase-1rq.2: Turn every red sase workflow green [in_progress]"]
    n3["sase-1rq.2.1: Turn every red sase workflow green [in_progress]"]
    n4["sase-1rq.2.1.1: Keep Master Gate green at the master tip [in_progress]"]
    n5["sase-1rq.2.1.2: Stop the coverage-contexts lane crashing on global disk patches [in_progress]"]
    n6["sase-1rq.2.1.3: Make the test-cost lane finish inside its 180-minute timeout [in_progress]"]
    n7["sase-1rq.2.1.4: Make the contention-test lane survive and pass [in_progress]"]
    n8["sase-1rq.2.1.5: Turn Full CI green alongside the sase-1r2.6 repair [in_progress]"]
    n9["sase-1rq.2.1.6: Clear CORE_LAG from Publish and the release PR floor smoke [in_progress]"]
    n10["sase-1rq.2.1.7: Confirm every in-scope workflow green and publish evidence [in_progress]"]
    n11["sase-1rq.3: Turn bob-cli CI green [in_progress]"]
    n12["sase-1rq.3.1: Turn bob-cli CI green on master [in_progress]"]
    n13["sase-1rq.3.1.1: Make the install_ui EarnedEta test hermetic to CARGO_INCREMENTAL [closed]"]
    n14["sase-1rq.3.1.2: Fix the known macOS-only test failures and the Google sign-in hang [closed]"]
    n15["sase-1rq.3.1.3: Run the full macOS CI test set to green on the mac host [in_progress]"]
    n16["sase-1rq.3.1.4: Confirm green CI on the master tip and publish evidence [in_progress]"]
    n17["sase-1rq.4: Turn bob-mac-capture CI green [in_progress]"]
    n18["sase-1rq.4.1: Turn bob-mac-capture master CI green [in_progress]"]
    n19["sase-1rq.4.1.1: Fix the eleven sigil-alias rewrite-lane tests that have never passed on CI [in_progress]"]
    n20["sase-1rq.4.1.2: Fix the Ctrl-H/L word-motion undo test [closed]"]
    n21["sase-1rq.4.1.3: Harden or quarantine the intermittent alias and card tests [in_progress]"]
    n22["sase-1rq.4.1.4: Drive master CI green and publish evidence [in_progress]"]
    n23["sase-1rq.5: Turn dotfiles CI green [closed]"]
    n0 --> n1
    n0 --> n2
    n2 --> n3
    n3 --> n4
    n3 --> n5
    n3 --> n6
    n3 --> n7
    n3 --> n8
    n3 --> n9
    n3 --> n10
    n0 --> n11
    n11 --> n12
    n12 --> n13
    n12 --> n14
    n12 --> n15
    n12 --> n16
    n0 --> n17
    n17 --> n18
    n18 --> n19
    n18 --> n20
    n18 --> n21
    n18 --> n22
    n0 --> n23
    n1 -.-> n2
    n4 -.-> n10
    n5 -.-> n10
    n6 -.-> n10
    n7 -.-> n10
    n8 -.-> n10
    n9 -.-> n10
    n13 -.-> n16
    n14 -.-> n15
    n14 -.-> n16
    n15 -.-> n16
    n19 -.-> n21
    n19 -.-> n22
    n20 -.-> n22
    n21 -.-> n22
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.1.md) | [sase-1rq.1](sase-1rq.1.md) | 0 |
| [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) | [sase-1rq.2](sase-1rq.2.md) | 0 |
| [bbugyi200.athena.sase-1rq.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.1/README.md) | [sase-1rq.2.1.1](sase-1rq.2.1.1.md) | 0 |
| [bbugyi200.athena.sase-1rq.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.2/README.md) | [sase-1rq.2.1.2](sase-1rq.2.1.2.md) | 0 |
| [bbugyi200.athena.sase-1rq.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.3/README.md) | [sase-1rq.2.1.3](sase-1rq.2.1.3.md) | 0 |
| [bbugyi200.athena.sase-1rq.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.4/README.md) | [sase-1rq.2.1.4](sase-1rq.2.1.4.md) | 0 |
| [bbugyi200.athena.sase-1rq.2.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.5/README.md) | [sase-1rq.2.1.5](sase-1rq.2.1.5.md) | 0 |
| [bbugyi200.athena.sase-1rq.2.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.6/README.md) | [sase-1rq.2.1.6](sase-1rq.2.1.6.md) | 0 |
| [bbugyi200.athena.sase-1rq.2.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.7/README.md) | [sase-1rq.2.1.7](sase-1rq.2.1.7.md) | 0 |
| [bbugyi200.athena.sase-1rq.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.3.md) | [sase-1rq.3](sase-1rq.3.md) | 0 |
| [bbugyi200.athena.sase-1rq.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3.1.1/README.md) | [sase-1rq.3.1.1](sase-1rq.3.1.1.md) | 0 |
| [bbugyi200.athena.sase-1rq.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3.1.2/README.md) | [sase-1rq.3.1.2](sase-1rq.3.1.2.md) | 0 |
| [bbugyi200.athena.sase-1rq.3.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.3.1.3.md) | [sase-1rq.3.1.3](sase-1rq.3.1.3.md) | 0 |
| [bbugyi200.athena.sase-1rq.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3.1.4/README.md) | [sase-1rq.3.1.4](sase-1rq.3.1.4.md) | 0 |
| [bbugyi200.athena.sase-1rq.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3.1.land/README.md) | [sase-1rq.3.1](sase-1rq.3.1.md) | 0 |
| [bbugyi200.athena.sase-1rq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.md) | [sase-1rq.4](sase-1rq.4.md) | 0 |
| [bbugyi200.athena.sase-1rq.4.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.1.1.md) | [sase-1rq.4.1.1](sase-1rq.4.1.1.md) | 0 |
| [bbugyi200.athena.sase-1rq.4.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.1.2.md) | [sase-1rq.4.1.2](sase-1rq.4.1.2.md) | 0 |
| [bbugyi200.athena.sase-1rq.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.4.1.3/README.md) | [sase-1rq.4.1.3](sase-1rq.4.1.3.md) | 0 |
| [bbugyi200.athena.sase-1rq.4.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.4.1.4/README.md) | [sase-1rq.4.1.4](sase-1rq.4.1.4.md) | 0 |
| [bbugyi200.athena.sase-1rq.4.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.4.1.land/README.md) | [sase-1rq.4.1](sase-1rq.4.1.md) | 0 |
| [bbugyi200.athena.sase-1rq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.5.md) | [sase-1rq.5](sase-1rq.5.md) | 0 |
| [bbugyi200.athena.sase-1rq.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.land/README.md) | [sase-1rq](README.md) | 0 |

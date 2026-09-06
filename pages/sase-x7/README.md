# Bead: sase-x7 — Canonical-only SASE across athena, mac, and apollo

[Bead Pages](../README.md) / sase-x7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gk.md) · **Assignee:** `sase-x7.land`
**Created:** 2026-09-05 18:55:26 EDT
**Plan:** [202609/canonical\_only\_fleet\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_only_fleet_cutover.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/canonical_only_fleet_cutover.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/canonical_only_fleet_cutover.md

<!-- sase:links:end -->

## Description

Migrate every fleet producer and live data store to canonical contracts, remove obsolete compatibility behavior from SASE and its coupled plugins, and verify the final installation on every machine while preserving historical records and a tested rollback.

## Notes

[2026-09-06T04:10:13Z · sase-x7.2.1.land] DISCOVERED ISSUE: the migration kit's 'procs-residue' operation cannot clear athena's real tasks.jsonl residue as scoped, because the canonical proc store keeps only a rolling recent window and every one of the 22 legacy rows is therefore unmatched. This is the kit refusing correctly, not a kit defect, but it means phase sase-x7.6 (local-state-cutover) inherits an unresolved residue class that needs either a human-verified manual archive path or a widened reconciliation rule in sase-core. Full evidence and the two options are recorded as a note on sase-x7.6. Found by sase-x7.2.1.4 on real athena data 2026-09-05; triaged here by sase-x7.2.1.land.

[2026-09-06T12:18:13Z · sase-x7.2.1.5.land] FOLLOW-UP ROUTING from child epic sase-x7.2.1.5: live core 0.32.23 on mac/apollo is a local-state-cutover precondition now recorded on sase-x7.6; Linux-hardcoded completion stamp targets in chezmoi source are canonical-producers work now recorded on sase-x7.3. The independent mac AXE stale-heartbeat/zero-runner-capacity defect became ready task sase-xd, related to sase-wd. No duplicate task beads were created for work already owned by this active epic.

[2026-09-06T12:19:01Z · sase-x7.2.1.5.land] FOLLOW-UP ROUTING from child epic sase-x7.2.1.5: live core 0.32.23 on mac/apollo is a local-state-cutover precondition now recorded on sase-x7.6; Linux-hardcoded completion stamp targets in chezmoi source are canonical-producers work now recorded on sase-x7.3. The independent mac AXE stale-heartbeat/zero-runner-capacity defect became ready task sase-xd, related to sase-wd. No duplicate task beads were created for work already owned by this active epic.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-x7.1](sase-x7.1.md) | Establish the complete compatibility and fleet inventory | ✓ closed | medium | 2026-09-05 | 1 | 0 |
| [sase-x7.10](sase-x7.10.md) | Delete renamed APIs, command aliases, and TUI test shims | ◐ in_progress | medium | 2026-09-05 | 1 | 0 |
| [sase-x7.11](sase-x7.11.md) | Delete completed local migrations and fallback storage roots | ◐ in_progress | medium | 2026-09-05 | 1 | 0 |
| [sase-x7.12](sase-x7.12.md) | Make configuration and prompt parsing canonical-only | ◐ in_progress | large | 2026-09-05 | 1 | 0 |
| [sase-x7.13](sase-x7.13.md) | Isolate immutable bead history decoding | ◐ in_progress | medium | 2026-09-05 | 1 | 0 |
| [sase-x7.14](sase-x7.14.md) | Close the compatibility inventory and add regression enforcement | ◐ in_progress | medium | 2026-09-05 | 1 | 0 |
| [sase-x7.15](sase-x7.15.md) | Deploy and validate the canonical-only fleet | ◐ in_progress | medium | 2026-09-05 | 1 | 0 |
| [sase-x7.2](sase-x7.2.md) | Build and rehearse the temporary migration tooling | ✓ closed | large | 2026-09-05 | 1 | 0 |
| [sase-x7.3](sase-x7.3.md) | Migrate configuration, prompts, editor integration, and automation | ◐ in_progress | large | 2026-09-05 | 1 | 0 |
| [sase-x7.4](sase-x7.4.md) | Move Telegram to the shared pending-action API | ◐ in_progress | medium | 2026-09-05 | 1 | 0 |
| [sase-x7.5](sase-x7.5.md) | Prepare canonical shared formats and coordinated wire contracts | ◐ in_progress | large | 2026-09-05 | 1 | 0 |
| [sase-x7.6](sase-x7.6.md) | Back up and migrate local state on all three machines | ◐ in_progress | medium | 2026-09-05 | 1 | 0 |
| [sase-x7.7](sase-x7.7.md) | Deploy Telegram and retire the second store | ◐ in_progress | medium | 2026-09-05 | 1 | 0 |
| [sase-x7.8](sase-x7.8.md) | Convert shared records and prove fleet convergence | ◐ in_progress | medium | 2026-09-05 | 1 | 0 |
| [sase-x7.9](sase-x7.9.md) | Remove legacy shared-format and cross-repo API branches | ◐ in_progress | large | 2026-09-05 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-x7: Canonical-only SASE across athena, mac, and apollo [in_progress]"]
    n1["sase-x7.1: Establish the complete compatibility and fleet inventory [closed]"]
    n2["sase-x7.10: Delete renamed APIs, command aliases, and TUI test shims [in_progress]"]
    n3["sase-x7.11: Delete completed local migrations and fallback storage roots [in_progress]"]
    n4["sase-x7.12: Make configuration and prompt parsing canonical-only [in_progress]"]
    n5["sase-x7.13: Isolate immutable bead history decoding [in_progress]"]
    n6["sase-x7.14: Close the compatibility inventory and add regression enforcement [in_progress]"]
    n7["sase-x7.15: Deploy and validate the canonical-only fleet [in_progress]"]
    n8["sase-x7.2: Build and rehearse the temporary migration tooling [closed]"]
    n9["sase-x7.2.1: Temporary offline migration kit for the canonical-only cutover [closed]"]
    n10["sase-x7.2.1.1: Land the migration wire contract and bindings in the Rust core [closed]"]
    n11["sase-x7.2.1.2: Build the backup and restore engine and the host drain inventory [closed]"]
    n12["sase-x7.2.1.3: Build the dry-run, apply, journal, and operation catalog [closed]"]
    n13["sase-x7.2.1.4: Rehearse the kit on real data across Linux and macOS [closed]"]
    n14["sase-x7.2.1.5: Finish the migration kit's macOS rehearsal leg and publish its acceptance evidence [closed]"]
    n15["sase-x7.2.1.5.1: Rehearse the migration kit on protected copies of mac's real data [closed]"]
    n16["sase-x7.2.1.5.2: Fold the mac results in and publish the four kit-rehearsal artifacts [closed]"]
    n17["sase-x7.3: Migrate configuration, prompts, editor integration, and automation [in_progress]"]
    n18["sase-x7.3.1: Canonical producer fleet migration [in_progress]"]
    n19["sase-x7.3.1.1: Canonicalize authoritative SASE producers [closed]"]
    n20["sase-x7.3.1.2: Canonicalize the Neovim integration [closed]"]
    n21["sase-x7.3.1.3: Canonicalize plugin prompts and callers [closed]"]
    n22["sase-x7.3.1.4: Regenerate canonical chezmoi sources [in_progress]"]
    n23["sase-x7.3.1.5: Deploy and verify the canonical fleet [in_progress]"]
    n24["sase-x7.4: Move Telegram to the shared pending-action API [in_progress]"]
    n25["sase-x7.5: Prepare canonical shared formats and coordinated wire contracts [in_progress]"]
    n26["sase-x7.6: Back up and migrate local state on all three machines [in_progress]"]
    n27["sase-x7.7: Deploy Telegram and retire the second store [in_progress]"]
    n28["sase-x7.8: Convert shared records and prove fleet convergence [in_progress]"]
    n29["sase-x7.9: Remove legacy shared-format and cross-repo API branches [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n8 --> n9
    n9 --> n10
    n9 --> n11
    n9 --> n12
    n9 --> n13
    n9 --> n14
    n14 --> n15
    n14 --> n16
    n0 --> n17
    n17 --> n18
    n18 --> n19
    n18 --> n20
    n18 --> n21
    n18 --> n22
    n18 --> n23
    n0 --> n24
    n0 --> n25
    n0 --> n26
    n0 --> n27
    n0 --> n28
    n0 --> n29
    n1 -.-> n8
    n1 -.-> n17
    n1 -.-> n24
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
    n5 -.-> n6
    n6 -.-> n7
    n8 -.-> n17
    n8 -.-> n24
    n8 -.-> n25
    n8 -.-> n26
    n10 -.-> n11
    n11 -.-> n12
    n12 -.-> n13
    n15 -.-> n16
    n17 -.-> n24
    n17 -.-> n26
    n19 -.-> n20
    n19 -.-> n21
    n20 -.-> n22
    n21 -.-> n22
    n22 -.-> n23
    n24 -.-> n25
    n24 -.-> n27
    n25 -.-> n28
    n26 -.-> n27
    n26 -.-> n28
    n27 -.-> n28
    n28 -.-> n29
    n29 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.1/README.md) | [sase-x7.1](sase-x7.1.md) | 0 |
| [bbugyi200.athena.sase-x7.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.10/README.md) | [sase-x7.10](sase-x7.10.md) | 0 |
| [bbugyi200.athena.sase-x7.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.11/README.md) | [sase-x7.11](sase-x7.11.md) | 0 |
| [bbugyi200.athena.sase-x7.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.12/README.md) | [sase-x7.12](sase-x7.12.md) | 0 |
| [bbugyi200.athena.sase-x7.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.13/README.md) | [sase-x7.13](sase-x7.13.md) | 0 |
| [bbugyi200.athena.sase-x7.14](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.14/README.md) | [sase-x7.14](sase-x7.14.md) | 0 |
| [bbugyi200.athena.sase-x7.15](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.15/README.md) | [sase-x7.15](sase-x7.15.md) | 0 |
| [bbugyi200.athena.sase-x7.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.md) | [sase-x7.2](sase-x7.2.md) | 0 |
| [bbugyi200.athena.sase-x7.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.2.1.1/README.md) | [sase-x7.2.1.1](sase-x7.2.1.1.md) | 2 |
| [bbugyi200.athena.sase-x7.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.2.1.2/README.md) | [sase-x7.2.1.2](sase-x7.2.1.2.md) | 1 |
| [bbugyi200.athena.sase-x7.2.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.1.3.md) | [sase-x7.2.1.3](sase-x7.2.1.3.md) | 1 |
| [bbugyi200.athena.sase-x7.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.2.1.4/README.md) | [sase-x7.2.1.4](sase-x7.2.1.4.md) | 1 |
| [bbugyi200.athena.sase-x7.2.1.5.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.1.5.1.md) | [sase-x7.2.1.5.1](sase-x7.2.1.5.1.md) | 0 |
| [bbugyi200.athena.sase-x7.2.1.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.2.1.5.2/README.md) | [sase-x7.2.1.5.2](sase-x7.2.1.5.2.md) | 0 |
| [bbugyi200.athena.sase-x7.2.1.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.1.5.land.md) | [sase-x7.2.1.5](sase-x7.2.1.5.md) | 0 |
| [bbugyi200.athena.sase-x7.2.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.1.land.md) | [sase-x7.2.1](sase-x7.2.1.md) | 0 |
| [bbugyi200.athena.sase-x7.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.3.md) | [sase-x7.3](sase-x7.3.md) | 0 |
| [bbugyi200.athena.sase-x7.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.3.1.1/README.md) | [sase-x7.3.1.1](sase-x7.3.1.1.md) | 1 |
| [bbugyi200.athena.sase-x7.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.3.1.2/README.md) | [sase-x7.3.1.2](sase-x7.3.1.2.md) | 0 |
| [bbugyi200.athena.sase-x7.3.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.3.1.3/README.md) | [sase-x7.3.1.3](sase-x7.3.1.3.md) | 1 |
| [bbugyi200.athena.sase-x7.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.3.1.4/README.md) | [sase-x7.3.1.4](sase-x7.3.1.4.md) | 0 |
| [bbugyi200.athena.sase-x7.3.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.3.1.5/README.md) | [sase-x7.3.1.5](sase-x7.3.1.5.md) | 0 |
| [bbugyi200.athena.sase-x7.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.3.1.land/README.md) | [sase-x7.3.1](sase-x7.3.1.md) | 0 |
| [bbugyi200.athena.sase-x7.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.4/README.md) | [sase-x7.4](sase-x7.4.md) | 0 |
| [bbugyi200.athena.sase-x7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.5/README.md) | [sase-x7.5](sase-x7.5.md) | 0 |
| [bbugyi200.athena.sase-x7.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.6/README.md) | [sase-x7.6](sase-x7.6.md) | 0 |
| [bbugyi200.athena.sase-x7.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.7/README.md) | [sase-x7.7](sase-x7.7.md) | 0 |
| [bbugyi200.athena.sase-x7.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.8/README.md) | [sase-x7.8](sase-x7.8.md) | 0 |
| [bbugyi200.athena.sase-x7.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.9/README.md) | [sase-x7.9](sase-x7.9.md) | 0 |
| [bbugyi200.athena.sase-x7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.land/README.md) | [sase-x7](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`13ebfeb`](https://github.com/sase-org/sase/commit/13ebfeb061db13fbcc2bea86a83727da6f8398ef) | test(core): require migration bindings in floor checks | [sase-x7.2.1.1](sase-x7.2.1.1.md) | 2026-09-05 20:31:29 EDT |
| sase-core | [`sase-core@1bf6023`](https://github.com/sase-org/sase-core/commit/1bf602388722385460c48d244d1e1571840a8922) | feat(migration): add offline migration wire contract | [sase-x7.2.1.1](sase-x7.2.1.1.md) | 2026-09-05 20:37:56 EDT |
| sase | [`43164ea`](https://github.com/sase-org/sase/commit/43164eace6ba51bce0ec00065f645e1ab78feac6) | feat(migrate): add sase migrate backup/restore and G3 fleet inventory | [sase-x7.2.1.2](sase-x7.2.1.2.md) | 2026-09-05 21:40:14 EDT |
| sase | [`bea92ce`](https://github.com/sase-org/sase/commit/bea92ce9287cec7250384a1fe88ba4fdcca4932b) | feat(migration-kit): add driver operation catalog | [sase-x7.2.1.3](sase-x7.2.1.3.md) | 2026-09-05 23:06:11 EDT |
| sase | [`16153bf`](https://github.com/sase-org/sase/commit/16153bf5606f085fcd1b13b58b188cb7eb4af954) | test(migration-kit): rehearse remaining synthetic edge-case matrix | [sase-x7.2.1.4](sase-x7.2.1.4.md) | 2026-09-05 23:53:32 EDT |
| sase | [`caa7917`](https://github.com/sase-org/sase/commit/caa7917ac966141b5cd6757e89ca245710e95950) | feat(cli): canonicalize host producers for the fleet cutover | [sase-x7.3.1.1](sase-x7.3.1.1.md) | 2026-09-06 09:54:28 EDT |
| sase-github | [`sase-github@095181a`](https://github.com/sase-org/sase-github/commit/095181a338bd8295e7b450d341b238e587a0d78a) | refactor(workspace): canonicalize Patch imports and drop ChangeSpec facade | [sase-x7.3.1.3](sase-x7.3.1.3.md) | 2026-09-06 10:20:28 EDT |

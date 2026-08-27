# Bead: sase-ug — A link rail on every tab

[Bead Pages](../README.md) / sase-ug

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eh.md) · **Assignee:** `sase-ug.land`
**Created:** 2026-08-26 14:48:23 EDT
**Plan:** [202608/link\_rail\_every\_tab.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_rail_every_tab.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202608/link_rail_every_tab.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202608/link_rail_every_tab.md

<!-- sase:links:end -->

## Description

Every ACE tab shows the selected entity's typed artifact links in one place, in one line, in the same place; `$` plus one key follows any of them across tabs and panes; the surface is invisible when the selection has no links; and the read model it draws from stops silently losing whole relation classes.

## Notes

[2026-08-26T20:50:33Z · sase-ud.3] DISCOVERED ISSUE: During gate_shell.md implementation verification on 2026-08-26, just check passed formatting, ruff, mypy, feature-flag, pyscript, test-wait, changelog, terminology, symvision, and toobig lints, then failed only SASE validation at init memory --check. The stale generated files are artifact-relation-specific: sase/artifact_relations.json (-32), sase/memory/sase_artifacts.md (-2), and sase/memory/README.md (+4 -4). Repro: just check, or .venv/bin/sase validate. This appears causally related to this epic's artifact-link/relation read-model work rather than the gate-shell diff; memory files were not regenerated because agent instructions require explicit user approval before changing SASE memory.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-ug.1](sase-ug.1.md) | One projection for the machine-local read model | ✓ closed | medium | 2026-08-26 | 1 | 1 |
| [sase-ug.10](sase-ug.10.md) | Retire the duplicates and land the rail | ◐ in_progress | medium | 2026-08-26 | 1 | 0 |
| [sase-ug.2](sase-ug.2.md) | A stale clone may not prove deletion | ✓ closed | medium | 2026-08-26 | 1 | 1 |
| [sase-ug.3](sase-ug.3.md) | Projected edges from facts SASE already owns | ✓ closed | large | 2026-08-26 | 1 | 2 |
| [sase-ug.4](sase-ug.4.md) | A way to read durable truth and see the drift | ✓ closed | medium | 2026-08-26 | 1 | 1 |
| [sase-ug.5](sase-ug.5.md) | One selected-entity ref and one O(1) link index | ✓ closed | medium | 2026-08-26 | 1 | 1 |
| [sase-ug.6](sase-ug.6.md) | The Link Rail, read-only | ✓ closed | medium | 2026-08-26 | 1 | 2 |
| [sase-ug.7](sase-ug.7.md) | The \`$\` grammar and a jump that always lands | ✓ closed | large | 2026-08-26 | 1 | 1 |
| [sase-ug.8](sase-ug.8.md) | Walking back across surfaces | ✓ closed | medium | 2026-08-26 | 1 | 1 |
| [sase-ug.9](sase-ug.9.md) | The \`$0\` Links panel | ✓ closed | medium | 2026-08-26 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ug: A link rail on every tab [in_progress]"]
    n1["sase-ug.1: One projection for the machine-local read model [closed]"]
    n2["sase-ug.10: Retire the duplicates and land the rail [in_progress]"]
    n3["sase-ug.2: A stale clone may not prove deletion [closed]"]
    n4["sase-ug.3: Projected edges from facts SASE already owns [closed]"]
    n5["sase-ug.4: A way to read durable truth and see the drift [closed]"]
    n6["sase-ug.5: One selected-entity ref and one O(1) link index [closed]"]
    n7["sase-ug.6: The Link Rail, read-only [closed]"]
    n8["sase-ug.7: The `$` grammar and a jump that always lands [closed]"]
    n9["sase-ug.8: Walking back across surfaces [closed]"]
    n10["sase-ug.9: The `$0` Links panel [closed]"]
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
    n1 -.-> n3
    n1 -.-> n4
    n1 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
    n6 -.-> n7
    n7 -.-> n8
    n8 -.-> n9
    n8 -.-> n10
    n9 -.-> n2
    n10 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ug.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ug.1/README.md) | [sase-ug.1](sase-ug.1.md) | 1 |
| [bbugyi200.athena.sase-ug.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ug.10/README.md) | [sase-ug.10](sase-ug.10.md) | 0 |
| [bbugyi200.athena.sase-ug.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ug.2/README.md) | [sase-ug.2](sase-ug.2.md) | 1 |
| [bbugyi200.athena.sase-ug.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ug.3.md) | [sase-ug.3](sase-ug.3.md) | 2 |
| [bbugyi200.athena.sase-ug.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ug.4/README.md) | [sase-ug.4](sase-ug.4.md) | 1 |
| [bbugyi200.athena.sase-ug.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ug.5/README.md) | [sase-ug.5](sase-ug.5.md) | 1 |
| [bbugyi200.athena.sase-ug.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ug.6/README.md) | [sase-ug.6](sase-ug.6.md) | 2 |
| [bbugyi200.athena.sase-ug.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ug.7.md) | [sase-ug.7](sase-ug.7.md) | 1 |
| [bbugyi200.athena.sase-ug.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ug.8.md) | [sase-ug.8](sase-ug.8.md) | 1 |
| [bbugyi200.athena.sase-ug.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ug.9/README.md) | [sase-ug.9](sase-ug.9.md) | 1 |
| [bbugyi200.athena.sase-ug.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ug.land/README.md) | [sase-ug](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`452ac54`](https://github.com/sase-org/sase/commit/452ac54cf967dae7f8974eec522dd564007d6545) | fix(sdd): converge artifact-link aggregate projections on one read model | [sase-ug.1](sase-ug.1.md) | 2026-08-26 15:15:17 EDT |
| sase | [`9a477bf`](https://github.com/sase-org/sase/commit/9a477bfd1cf8f3aa1fec9e1eae900c9f3cb3970a) | fix(artifact-links): require fresh deletion authority | [sase-ug.2](sase-ug.2.md) | 2026-08-26 15:40:59 EDT |
| sase | [`4bce1a4`](https://github.com/sase-org/sase/commit/4bce1a4f68d985c623611416ea8187da7052609f) | feat(artifact-links): project recomputed edges into the read model (sase-ug.3) | [sase-ug.3](sase-ug.3.md) | 2026-08-26 18:45:13 EDT |
| sase-core | [`sase-core@917951d`](https://github.com/sase-org/sase-core/commit/917951d207b47099162423247c1811bcdf6aa31a) | feat(artifact-links): add projection relation builtins | [sase-ug.3](sase-ug.3.md) | 2026-08-26 18:49:40 EDT |
| sase | [`58e5a83`](https://github.com/sase-org/sase/commit/58e5a8310e26bd823209156c8890ee4fcb2ddfef) | feat(artifact-links): add durable truth drift reporting | [sase-ug.4](sase-ug.4.md) | 2026-08-26 20:32:42 EDT |
| sase | [`38c1588`](https://github.com/sase-org/sase/commit/38c15881ed3047ff976883b56f7e3e17c10f0af5) | feat(artifact-links): add link subject resolution and follow-link action wiring | [sase-ug.5](sase-ug.5.md) | 2026-08-26 21:26:56 EDT |
| sase | [`48e019a`](https://github.com/sase-org/sase/commit/48e019af82f279fc51d53d0e1f1ec51123bebd80) | feat(ace): add read-only link rail | [sase-ug.6](sase-ug.6.md) | 2026-08-26 22:22:44 EDT |
| sase--agents | [`sase--agents@b438c6d`](https://github.com/sase-org/sase--agents/commit/b438c6dea33ab4a04d4800ef29acf6b501c24333) | chore(agents): archive link rail prompt | [sase-ug.6](sase-ug.6.md) | 2026-08-26 22:25:24 EDT |
| sase | [`d070280`](https://github.com/sase-org/sase/commit/d07028050cb831849d1e666ab267a39223779f9b) | feat(tui): add link-follow key grammar | [sase-ug.7](sase-ug.7.md) | 2026-08-26 23:45:35 EDT |
| sase | [`e8f30d2`](https://github.com/sase-org/sase/commit/e8f30d25fba529b2cf16d755fd632915a8f53efe) | feat(ace): add artifact links panel | [sase-ug.9](sase-ug.9.md) | 2026-08-27 00:44:25 EDT |
| sase | [`d8e8b5a`](https://github.com/sase-org/sase/commit/d8e8b5ab8ed264a983fd892b29d8e6f752428a93) | feat(tui): add app-level link trail for Ctrl+O/Ctrl+Shift+O across tabs | [sase-ug.8](sase-ug.8.md) | 2026-08-27 01:04:08 EDT |

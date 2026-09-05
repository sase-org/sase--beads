# Bead: sase-ws — Remove The Agents-Sync Import Leg

[Bead Pages](../README.md) / sase-ws

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.kellys\_mbp.y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.kellys_mbp.y.md) · **Assignee:** `sase-ws.land`
**Created:** 2026-09-04 13:48:25 EDT
**Plan:** [202609/remove\_agents\_sync\_import.md](https://github.com/sase-org/sase--plans/blob/main/202609/remove_agents_sync_import.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/remove_agents_sync_import.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/remove_agents_sync_import.md

<!-- sase:links:end -->

## Description

Syncing agents from remote machines to local disk is completely removed: no import engine, no incoming cache, no ACE import surfaces, no import config keys, flags, docs, or memory references, and locally materialized imported state has one explicit cleanup path. The agents-sidecar publication leg (prompt archive, agent pages, provenance links, Referenced By write-backs) keeps working unchanged.

## Notes

[2026-09-04T23:31:51Z · sase-w8.4.land] DISCOVERED ISSUE: sase-ws.1 (61d72860a) removed the 'agents.cached' ProcProducerSite from src/sase/ace/tui/_proc_producer_sites_actions.py but did not update the hardcoded inventory count, so tests/ace/tui/test_proc_producer_inventory.py::test_inventory_records_infrastructure_and_classifications now fails with 'assert 42 == 43' at tests/ace/tui/test_proc_producer_inventory.py:317. Reproduced deterministically on clean master c0b741c93 with a freshly reinstalled venv, serially under -p no:randomly; independently observed earlier by phase agent sase-w8.4.1 in a separate full-suite run. This is a true failure, not a flake: the assertion compares len(PRODUCTION_PRODUCERS) against a literal. Fix belongs to this epic (change 43 -> 42, or to a computed expectation) since sase-ws.1 caused it. Reported by the sase-w8.4 land agent.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-ws.1](sase-ws.1.md) | Remove ACE import surfaces | ✓ closed | large | 2026-09-04 | 1 | 1 |
| [sase-ws.2](sase-ws.2.md) | Rescope sase agent sync to publication | ✓ closed | medium | 2026-09-04 | 1 | 1 |
| [sase-ws.3](sase-ws.3.md) | One explicit purge for imported local state | ◐ in_progress | medium | 2026-09-04 | 0 | 0 |
| [sase-ws.4](sase-ws.4.md) | Delete the import engine and v1 leg | ◐ in_progress | large | 2026-09-04 | 0 | 0 |
| [sase-ws.5](sase-ws.5.md) | Drop orphaned Rust import APIs | ◐ in_progress | medium | 2026-09-04 | 0 | 0 |
| [sase-ws.6](sase-ws.6.md) | Docs, memory record, and final sweep | ◐ in_progress | medium | 2026-09-04 | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ws: Remove The Agents-Sync Import Leg [in_progress]"]
    n1["sase-ws.1: Remove ACE import surfaces [closed]"]
    n2["sase-ws.2: Rescope sase agent sync to publication [closed]"]
    n3["sase-ws.3: One explicit purge for imported local state [in_progress]"]
    n4["sase-ws.4: Delete the import engine and v1 leg [in_progress]"]
    n5["sase-ws.5: Drop orphaned Rust import APIs [in_progress]"]
    n6["sase-ws.6: Docs, memory record, and final sweep [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.kellys\_mbp.sase-ws.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.kellys_mbp.sase-ws.1.md) | [sase-ws.1](sase-ws.1.md) | 0 |
| [bbugyi200.kellys\_mbp.sase-ws.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.kellys_mbp.sase-ws.2/README.md) | [sase-ws.2](sase-ws.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`61d7286`](https://github.com/sase-org/sase/commit/61d72860a1a8b636c0f8ec4e1a6d15d6172db054) | feat: Remove ACE agents-sync import surfaces (sase-ws.1) | [sase-ws.1](sase-ws.1.md) | 2026-09-04 14:58:26 EDT |
| sase | [`470442d`](https://github.com/sase-org/sase/commit/470442d3d828e720d99d44c7a0f305dfc225e3ff) | feat(agent-sync): make sync publication-only | [sase-ws.2](sase-ws.2.md) | 2026-09-05 06:13:38 EDT |

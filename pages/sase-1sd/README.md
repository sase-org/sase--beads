# Bead: sase-1sd — Next seven: salvage the display-name fix, then unstrand the fleet (sase-zo, sase-1s2, sase-1re, sase-1o1, sase-1qm, sase-1qi, sase-1db)

[Bead Pages](../README.md) / sase-1sd

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.land`
**Created:** 2026-11-12 05:26:15 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/next_seven_salvage_and_unstrand.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md

<!-- sase:links:end -->

## Description

Complete and close the seven ready task beads ranked by the 202611 next-seven research report, running the phases strictly one at a time.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1sd.1](sase-1sd.1.md) | Salvage and land the verified -p display-name resolution fix (sase-zo) | ✓ closed | medium | 2026-11-12 | 1 | 1 |
| [sase-1sd.2](sase-1sd.2.md) | Stop runner module imports from replacing the process SIGTERM handler (sase-1s2) | ◐ in_progress | small | 2026-11-12 | 1 | 1 |
| [sase-1sd.3](sase-1sd.3.md) | Stop done monitors with stale followup\_pending from owning beads forever (sase-1re) | ◐ in_progress | medium | 2026-11-12 | 0 | 0 |
| [sase-1sd.4](sase-1sd.4.md) | Stop continuation capture from nesting fork ancestry past the 256 KiB cap (sase-1o1) | ◐ in_progress | large | 2026-11-12 | 0 | 0 |
| [sase-1sd.5](sase-1sd.5.md) | Stop host completion from refusing checks that passed (sase-1qm) | ◐ in_progress | large | 2026-11-12 | 0 | 0 |
| [sase-1sd.6](sase-1sd.6.md) | Make sase agent restart find crash-killed agents (sase-1qi, ride-along sase-1qr) | ◐ in_progress | medium | 2026-11-12 | 0 | 0 |
| [sase-1sd.7](sase-1sd.7.md) | Verify an existing attachments-private remote is actually private before pushing (sase-1db) | ◐ in_progress | medium | 2026-11-12 | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1sd: Next seven: salvage the display-name fix, then unstrand the fleet (sase-zo, sase-1s2, sase-1re, sase-1o1, sase-1qm, sase-1qi, sase-1db) [in_progress]"]
    n1["sase-1sd.1: Salvage and land the verified -p display-name resolution fix (sase-zo) [closed]"]
    n2["sase-1sd.2: Stop runner module imports from replacing the process SIGTERM handler (sase-1s2) [in_progress]"]
    n3["sase-1sd.3: Stop done monitors with stale followup_pending from owning beads forever (sase-1re) [in_progress]"]
    n4["sase-1sd.4: Stop continuation capture from nesting fork ancestry past the 256 KiB cap (sase-1o1) [in_progress]"]
    n5["sase-1sd.5: Stop host completion from refusing checks that passed (sase-1qm) [in_progress]"]
    n6["sase-1sd.6: Make sase agent restart find crash-killed agents (sase-1qi, ride-along sase-1qr) [in_progress]"]
    n7["sase-1sd.7: Verify an existing attachments-private remote is actually private before pushing (sase-1db) [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
    n5 -.-> n6
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sd.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sd.1.md) | [sase-1sd.1](sase-1sd.1.md) | 1 |
| [bbugyi200.athena.sase-1sd.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sd.2.md) | [sase-1sd.2](sase-1sd.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e072729`](https://github.com/sase-org/sase/commit/e07272959937e0a39e1b7c31254b252e657978be) | fix(repo): resolve -p project ref through registry display names and aliases | [sase-1sd.1](sase-1sd.1.md) | 2026-11-12 06:01:49 EST |
| sase | [`063c982`](https://github.com/sase-org/sase/commit/063c98293b69f23543c91d66709a2b28eaa310a1) | fix(axe): install SIGTERM handlers in runner main, not at import | [sase-1sd.2](sase-1sd.2.md) | 2026-11-12 06:59:06 EST |

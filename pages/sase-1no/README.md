# Bead: sase-1no — Flag stranded epic work in ACE

[Bead Pages](../README.md) / sase-1no

**Status:** ○ open · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13e.md) · **Assignee:** `sase-1no.land`
**Created:** 2026-10-23 14:22:48 EDT
**Plan:** [202610/stranded\_epic\_work.md](https://github.com/sase-org/sase--plans/blob/main/202610/stranded_epic_work.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/stranded_epic_work.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/stranded_epic_work.md

<!-- sase:links:end -->

## Description

An in_progress phase or epic bead that nothing will ever resume can no longer sit unnoticed. sase-core classifies it once. ACE flags it with a single amber ⚐ vocabulary on the stuck row, on everything waiting on it, on its epic clans, and in the Beads pane, and any flagged row resolves it with one keystroke.

## Notes

[2026-10-23T22:20:33Z · sase-1n6.5.1.5.2.1.land] DISCOVERED ISSUE: integration audit by sase-1n6.5.1.5.2.1.land at 2d1e7fd486. Your collect commit 5d982d2bb9 moves sase-core-revision.txt to 58aca5fe69158286092e3a33685687a52f8d2b8f and adds required stranded_work_reduce, while pyproject/uv.lock still pin published 0.42.2. Isolated published preflight: uv run --no-project --isolated --with sase-core-rs==0.42.2 python tools/check_sase_core_rs_bindings exits 1, missing 1 of 876: stranded_work_reduce. Opened core checkout has no tag containing 58aca5fe; v0.42.2 contains the earlier proof pin 246e2874 only. This newly landed feature prevents a green published qualification at current master. The qualification remaining-work plan will wait for the authorized daily core cut and integrate a complete containing exact published pin before reproof; do not duplicate that pin work. No binding bypass or source fallback is permitted.

[2026-10-24T06:39:39Z · sase-1nn.8.land] DISCOVERED ISSUE from sase-1nn.8.1 note 1, independently verified by sase-1nn.8.land: bb81495765 (sase-1no.3) adds three Help legend rows without updating agents_archive_help_120x40.png. Full CI 40063272183, job 120783473777 at 102c6ee847 reports exactly 52757/1520532 changed pixels; prior Full CI 40054807788 reports the same delta. This blocks the 0.18.1 release. The remaining-work child plan under sase-1nn.8 will repair this golden using deterministic local capture and inspect Archive visibility; do not duplicate that repair. The published-core gap in note 1 is resolved: dd0c6d8d19 pins complete PyPI 0.42.3, tag f726ca1e contains 58aca5fe, and an isolated binding probe passes all 876 bindings.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1no.1](sase-1no.1.md) | Stranded-work reducer in sase-core | ✓ closed | medium | 2026-10-23 | 1 | 1 |
| [sase-1no.2](sase-1no.2.md) | Python fact collector, facade, presentation vocabulary, and doctor | ✓ closed | medium | 2026-10-23 | 1 | 1 |
| [sase-1no.3](sase-1no.3.md) | Agents tab rows, clans, waiters, and info strip | ✓ closed | medium | 2026-10-23 | 1 | 1 |
| [sase-1no.4](sase-1no.4.md) | Agents detail callouts, toast, and query field | ✓ closed | small | 2026-10-23 | 1 | 1 |
| [sase-1no.5](sase-1no.5.md) | Beads pane stranded badges | ✓ closed | small | 2026-10-23 | 1 | 1 |
| [sase-1no.6](sase-1no.6.md) | One-keystroke resolution from any flagged row | ◐ in_progress | medium | 2026-10-23 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1no: Flag stranded epic work in ACE [open]"]
    n1["sase-1no.1: Stranded-work reducer in sase-core [closed]"]
    n2["sase-1no.2: Python fact collector, facade, presentation vocabulary, and doctor [closed]"]
    n3["sase-1no.3: Agents tab rows, clans, waiters, and info strip [closed]"]
    n4["sase-1no.4: Agents detail callouts, toast, and query field [closed]"]
    n5["sase-1no.5: Beads pane stranded badges [closed]"]
    n6["sase-1no.6: One-keystroke resolution from any flagged row [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n2 -.-> n3
    n2 -.-> n5
    n3 -.-> n4
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1no.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1no.1/README.md) | [sase-1no.1](sase-1no.1.md) | 1 |
| [bbugyi200.athena.sase-1no.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1no.2.md) | [sase-1no.2](sase-1no.2.md) | 1 |
| [bbugyi200.athena.sase-1no.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1no.3/README.md) | [sase-1no.3](sase-1no.3.md) | 1 |
| [bbugyi200.athena.sase-1no.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1no.4.md) | [sase-1no.4](sase-1no.4.md) | 1 |
| [bbugyi200.athena.sase-1no.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1no.5.md) | [sase-1no.5](sase-1no.5.md) | 1 |
| [bbugyi200.athena.sase-1no.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1no.6/README.md) | [sase-1no.6](sase-1no.6.md) | 0 |
| [bbugyi200.athena.sase-1no.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1no.land/README.md) | [sase-1no](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@58aca5f`](https://github.com/sase-org/sase-core/commit/58aca5fe69158286092e3a33685687a52f8d2b8f) | feat(stranded-work): add pure facts-to-verdicts reducer with PyO3 binding | [sase-1no.1](sase-1no.1.md) | 2026-10-23 15:03:40 EDT |
| sase | [`5d982d2`](https://github.com/sase-org/sase/commit/5d982d2bb9241a5b4e3db8baf38d0cae7ebeb53f) | feat(beads): collect stranded-work facts and doctor WARNING | [sase-1no.2](sase-1no.2.md) | 2026-10-23 17:21:03 EDT |
| sase | [`bb81495`](https://github.com/sase-org/sase/commit/bb81495765e9afe676552b285c8e487b1a144814) | feat(agents): show stranded bead work in agent rows | [sase-1no.3](sase-1no.3.md) | 2026-10-23 18:22:50 EDT |
| sase | [`a7996c3`](https://github.com/sase-org/sase/commit/a7996c3b77d155a9b3449d97b5e79b46b0ddd7f3) | feat(ace): show stranded work in agent details | [sase-1no.4](sase-1no.4.md) | 2026-10-23 20:06:53 EDT |
| sase | [`c793bff`](https://github.com/sase-org/sase/commit/c793bff54b0382194527c3c422b0416b11d87a1f) | feat(tui): flag stranded work in the Beads pane | [sase-1no.5](sase-1no.5.md) | 2026-10-24 06:53:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1no.2--5][1] | Need parent epic DECISIONS and phase list to confirm collect-phase completeness | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1no.2.md

<!-- sase:referenced-by:end -->

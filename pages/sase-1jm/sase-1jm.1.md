# Bead: sase-1jm.1 — Archive index v3 and honest timestamps

[Bead Pages](../README.md) / [sase-1jm](README.md) / sase-1jm.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.45.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.45.linker.w0.md) · **Assignee:** `sase-1jm.1` · **Size:** medium
**Created:** 2026-10-10 06:41:07 EDT · **Closed:** 2026-10-10 07:05:04 EDT
**Plan:** [202610/agents\_archive\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view.md)

## Description

archive-index: bump the dismissed-bundle summary index to v3. Add the session, clan, agent-tab, and tribe columns the Archive groups and filters on. Record a real dismissed_at on every new bundle. Rebuild newest shard first, off the startup path, with cheap progress. Make the catalog accept every supported artifact-index schema version instead of one exact match.

## Notes

[2026-10-10T10:54:12Z · sase-1jm.1] PROGRESS: 47,000 synthetic bundle rebuild indexed all 47,000 rows in 8.112 s; fixture generation took 5.024 s and was excluded from rebuild timing. Targeted tests passed: 98 passed, 3 deselected; startup-sync coverage emitted one existing coroutine RuntimeWarning.

[2026-10-10T11:04:55Z · sase-1jm.1] PROPOSED FOLLOW-UP: Finish compatibility cleanup in active bead sase-1jc.5: remove the surviving registry definitions for closed flag beads sase-18l and sase-1ar; these unchanged base-tree inputs make just check rule 7 report both residue errors.

[2026-10-10T11:05:04Z · sase-1jm.1] Verified 91 targeted tests pass, just fmt and mypy pass, 47,000 synthetic archive bundles index in 8.1s, and git diff --check is clean. just check remains blocked only by rule 7 for closed flags sase-18l and sase-1ar; recorded the existing cleanup owner sase-1jc.5 as a proposed follow-up. epic-symbols reported no leftovers.

## Dependencies

- **Blocks:** [sase-1jm.2](sase-1jm.2.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.1/README.md) | [sase-1jm.1](sase-1jm.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e200cf6`](https://github.com/sase-org/sase/commit/e200cf6d677fcb6473d070d6a9a800f088eac3e6) | feat(agents): add v3 dismissed archive index | [sase-1jm.1](sase-1jm.1.md) | 2026-10-10 07:06:42 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.1/README.md

<!-- sase:referenced-by:end -->

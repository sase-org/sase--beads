# Bead: sase-1m3.6 — Agent directory join and the committed-plans facet

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.6` · **Size:** medium
**Created:** 2026-10-16 22:05:23 EDT · **Closed:** 2026-10-17 08:23:46 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

core-attribution: build the read-only agent directory from agents-sidecar pages and the local run index for attribution steps 2-4, and count committed plans (rename-aware first adds) credited to the proposing model.

## Notes

[2026-10-17T12:12:36Z · sase-1m3.6] PROPOSED FOLLOW-UP: skipped decisions-web record (stats_decision_record=no) — stats count each fact at its durable source, and footers stamp only underivable facts

[2026-10-17T12:12:48Z · sase-1m3.6] Directory measure on sase agents sidecar (debug test profile): 17273 pages, 7338 SHAs, 0 issues; cold 5601.4ms, warm median 444.1ms. Isolated git cat-file of 34546 meta+commits blobs is 621ms. Release --ignored LTO compile of sase_core tests was SIGKILL/OOM.

[2026-10-17T12:23:46Z · sase-1m3.6] Verified in sase-core: directory join (SHA, --code, page_metadata_empty, session_ambiguous, index-only, published-wins) and plan facet (rename first-add, exclusions, no double-count, re-proposal, local null, project_filter, --plan lookup). just test -p sase_core project_stats green; clippy -p sase_core green; sase tool run check fa8accac5ed226d7781647de443d54ab green. Agents sidecar measure: 17273 pages, cold 5601ms debug / warm 444ms. No leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1m3.10](sase-1m3.10.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1m3.11](sase-1m3.11.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1m3.4](sase-1m3.4.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.6/README.md) | [sase-1m3.6](sase-1m3.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7a46109`](https://github.com/sase-org/sase-core/commit/7a46109f2abf81d5251334088331f1ef96c917ae) | feat(project-stats): join the agent directory and count committed plans | [sase-1m3.6](sase-1m3.6.md) | 2026-10-17 08:43:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1m3.6][1] | Confirm the phase bead stayed closed after final submit | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.6/README.md

<!-- sase:referenced-by:end -->

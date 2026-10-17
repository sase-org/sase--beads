# Bead: sase-1m3.4.1 — Project statistics core engine for sase-1m3.4

[Bead Pages](../README.md) / [sase-1m3.4](sase-1m3.4.md) / sase-1m3.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1m3.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.4.md) · **Assignee:** `sase-1m3.4.1.land`
**Created:** 2026-10-16 22:16:00 EDT · **Closed:** 2026-10-17 02:47:51 EDT
**Plan:** [202610/project\_stats\_core\_engine.md](https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_core_engine.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/project_stats_core_engine.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_core_engine.md

<!-- sase:links:end -->

## Description

Complete the Rust project_stats API, hardened Git execution, cached full-DAG history, Output and lifetime aggregation, and Python binding required by sase-1m3.4, leaving stable extension points for its sibling facets.

## Notes

[2026-10-17T05:52:34Z · sase-1m3.4.1.land] FOLLOW-UP TRIAGE COMPLETE: Reviewed every child note. The four Clippy proposals (sase-1m3.4.1.1 note 1, .2 note 2, .3 note 1, .4 note 1) are one existing issue, corroborated with +1 on sase-1an. At core be2bfbee, classify.rs:500-502 still contains the exact expression and was last changed by 98c3682f; no fresh compiler run was claimed. The legacy batch migration proposed by sase-1m3.4.1.2 note 1 is new ready medium bug task sase-1mb: unchanged read_blobs and batched_diff_tree both synchronously write before stdout reading. Independent protocol reproduction left both writers blocked after 750ms despite a 100ms per-loop deadline, unblocked by killing/reaping Git. Source snapshots file:explicit:e8cdcc93ea565e0cc650ad8d and file:explicit:8ed243df05c3e11469a2e8d8 are attached to that task. Same-type and all-type searches, last-week sweep, and active-epic scope review found no duplicate or causal owner; the parent expressly defers these pre-existing callers. No other child follow-up was proposed or declined. The parent-phase skipped decision-record proposal remains deliberately unimplemented under final stats_decision_record=no; no memory change or duplicate task was created. Copy these outcomes into the final close note.

[2026-10-17T05:53:13Z · sase-1m3.4.1.land] LAND AUDIT — NOT READY TO CLOSE: Reviewed every note on phases .1-.4, both audited plans, actual Rust source and commits ac370734/b0cd62b9/855ed4c3/be2bfbee. Parent DECISIONS honored: no memory changes; Code/Runs/plans remain explicit unimplemented seams and no Python caller exists. Source findings: query.rs collect_portfolio_code skips later history rows after identity/common-dir coverage dedupe, losing divergent selected refs from portfolio totals; coverage also counts duplicate declared identities across clones. load_unique_sources shares whole WalkedSource values, leaking the first ref alias and issue.repo into later specs. All-unavailable Output/lifetime uses measured zero because count fields are nonnullable and empty rows always aggregate; failed walks are treated as partial measured histories. mod.rs contains context structs and impl rather than only facade declarations/re-exports. The manual benchmark resolves to sase-core, independently checked by resolving its candidate paths; .4 measured 1568 core commits, not the required sase history. These remain epic work, addressed by the validated medium tale sase_plan_project_stats_core_landing.md, whose final step performs this epic and parent-phase closeout without waiting for its own commit. Integration review: core intervening 305b7b80 adds proposed_with for the later plans facet; sase 7545e85abf provenance is already compatible with footer parsing; 7c6b32457b inventory is for the later loader; 315092afeb repairs the parent .1/.2 fixtures as parent notes confirm. Other post-start commits concern docs/checks/release/UI. Both reviewed checkouts are on master, with no extra local origin/master commits at audit time. Current epic-symbols is empty. No fresh Rust compiler/gate pass claimed during this static landing audit; the tale must test regressions, measure actual sase, run guarded just check, and verify symbols before closing. Follow-up triage is complete in the preceding note; do not duplicate sase-1an or sase-1mb.

[2026-10-17T06:47:51Z · sase-1m3.4.1.land] Landing repairs for sase-1m3.4.1 are complete. No distinct tale child bead existed; this close covers the inherited epic after the four original phases (.1–.4) stayed closed.

Repairs in linked sase-core:
- Source metadata, history reuse, and coverage identity are separate. Query always SHA-unions non-failed selected code histories; coverage/measurement unique by repository identity (path when unresolved); history cache key remains identity+common-dir+tip. Specs keep their own ref names and issue.repo. Worst-health wins so spec order cannot hide a partial/unavailable clone.
- Output/lifetime counts are nullable. Wholly unavailable sources serialize JSON null with empty models; empty repos and empty ranges stay measured 0; mixed success keeps numeric subtotals. Failed walks (HistoryOutcome.failed) are unavailable, not partial-with-zeros; truncated walks with complete records stay unfailed.
- Facet types moved to project_stats/facet.rs; mod.rs is declarations and re-exports only.
- Equal-tip complete cache hits skip persist; persist updates the process memo instead of evicting it; complete outcomes are interned across queries. Sole-repo project aggregates reuse the repo measurement.
- Manual acceptance requires PROJECT_STATS_SASE_REPO (non-SASE_ prefix), validates the sase primary (src/sase + sase-core-revision.txt, rejects sase-core), and does not fall back.

Verification:
- just fmt; just test -p sase_core project_stats: 52 passed, 1 ignored; just test -p sase_core_py project_stats: 4 passed including null JSON; just test -p sase_core file_history: 46 passed.
- Ignored acceptance against this sase checkout (PROJECT_STATS_SASE_REPO): identity_ref=HEAD, history_commits=16215, range_commits=1865, tip=315092afebe542524e37d6b69c27030b77e02c2d, budget_ms=30000, max_bytes=33554432, cold_ms=1473.0, warm_median_ms=134.8 (under 150 ms), temporary cache, includes_extension_startup=false. Cold/warm fingerprints and Output/lifetime matched.
- sase tool run check 31b152b8a1c739389915263e812608ea exited 101 at clippy. Failure is clippy::nonminimal_bool at crates/sase_core/src/project_onboarding/classify.rs:500-502 on rustc 1.95. That file is absent from this diff; last change 98c3682f; HEAD be2bfbee still has the exact expression. Owned by ready CI task sase-1an (already +1 from this epic's land audit). Parent baseline-failure policy: record, do not keep the phase open, do not refile. Focused project_stats/file_history/binding tests on the repaired tree were green.

Follow-up outcomes (reuse land-audit note, not refiled): Clippy → sase-1an; legacy batch deadlock → ready bug sase-1mb. stats_decision_record=no: no memory edits. Code/Runs/directory/plans remain explicit null/empty seams. No sase Python caller, CLI, UI, dependency, or pin change. epic-symbols sase-1m3.4.1: none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.4.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.4.1.land.md) | [sase-1m3.4.1](sase-1m3.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8df5efd`](https://github.com/sase-org/sase-core/commit/8df5efda95b48fdb7e23d9ca3c66fc8a92118235) | fix(project-stats)!: distinguish unavailable counts from measured zeros | [sase-1m3.4.1](sase-1m3.4.1.md) | 2026-10-17 03:26:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1m3.4.1.1--1][1] | Need controlling epic decisions and remaining phase notes before closing child phase | 1 |
| read-by | [agent:sase-1m3.4.1.3][2] | Need the epic decisions governing this phase | 2 |
| read-by | [agent:sase-1m3.4.1.4][3] | Need parent epic DECISIONS and remaining work for query-binding phase | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.4.1.1.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.4.1.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.4.1.4/README.md

<!-- sase:referenced-by:end -->

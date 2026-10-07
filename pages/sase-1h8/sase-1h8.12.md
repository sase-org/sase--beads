# Bead: sase-1h8.12 — Indexed queries over the read model

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.12` · **Size:** medium
**Created:** 2026-10-06 18:59:45 EDT · **Closed:** 2026-10-07 15:49:22 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

read-model-queries: serve detail, ready, blocked, list, stats, resolve, search, and multi-get from indexed read-model tables so hot queries touch only active or requested rows.

## Notes

[2026-10-07T18:24:48Z · sase-1h8.12] PROPOSED FOLLOW-UP: sase-core editor::directive::tests::contract_covers_the_audited_directive_matrix fails identically on the clean base tree (extra for_epic directive); unrelated to read-model-queries, needs triage by the owning phase

[2026-10-07T18:34:31Z · sase-1h8.12] PROPOSED FOLLOW-UP: sase-core-py editor_completion directive_contract test fails identically on the clean base tree (same for_epic matrix drift as the sase_core editor::directive failure); unrelated to read-model-queries

[2026-10-07T19:48:45Z · sase-1h8.12--1] Phase work landed (UNCOMMITTED; land agent owns commit+pin, sase-core-revision.txt untouched). sase-core: new read_model/queries.rs, schema v2, bead_list_query/bead_statuses_for_ids/bead_closed_ids bindings, extended parity harness. Python: facade list_issue_page/statuses_for_ids/closed_ids, store_locator multi-get + closed-ids, cli_query pushdown, epic_from_plan children, new tests/test_bead_list_query.py. Verified: pytest tests/test_bead_list_query.py + tests/test_bead_statuses_for_project.py = 10 passed; sase-core bead_read_model_parity = 6 passed. Bench (SASE_BEAD_BENCH_STORE corpora, --nocapture; check.sh unsets SASE_* so direct cargo test was used): 1x (6899 issues, 6338 closed): read-model replay 1609ms cold-rebuild 280ms warm [250,253,258,260,269]ms tail 290ms cache 16MB; indexed point [1.1,1.1,1.1,1.2,1.4]ms ready(41) [6.0,6.0,6.1,6.3,6.3]ms list [388,396,403,403,409]ms closed20 [10.8,10.9,10.9,11.0,12.4]ms. 8x (55516 issues, 51320 closed): replay 14060ms cold 2346ms warm [2183,2286,2317,2327,2370]ms tail 2483ms cache 131MB; point [1.1,1.1,1.1,1.1,2.1]ms ready(312) [34.3,34.4,34.5,35.1,35.1]ms list [3213,3336,3414,3553,3625]ms closed20 [74.4,74.7,74.9,76.0,194.0]ms. Point/ready/closed20 stay flat vs 8x history growth.

[2026-10-07T19:49:08Z · sase-1h8.12--1] PROPOSED FOLLOW-UP: full `sase tool run check` (monitor 6fdaasfc00mq) TIMED OUT after 55m (exit -9, SIGTERM at check line 771 during test phase) — no test failures observed before the kill; all completed gates passed except lint-symvision `_runs` private-import errors in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py, both byte-identical to HEAD with lint config identical to HEAD, so pre-existing and unrelated to this phase; needs triage by the owning phase

[2026-10-07T19:49:22Z · sase-1h8.12--1] Indexed read-model queries verified: focused pytest 10 passed, sase-core parity 6 passed, bench point/ready/closed20 flat at 1x (6899 issues) and 8x (55516 issues); full-check timeout+symvision triaged as pre-existing PROPOSED FOLLOW-UP; no epic-symbol leftovers; pin untouched for land agent

## Dependencies

- **Blocks:** [sase-1h8.13](sase-1h8.13.md) ◐ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.7](sase-1h8.7.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.9](sase-1h8.9.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.12.md) | [sase-1h8.12](sase-1h8.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d2a56b4`](https://github.com/sase-org/sase-core/commit/d2a56b4ca928c602379619bb35869d133df9800e) | feat(bead): add indexed read-model query layer with Python bindings | [sase-1h8.12](sase-1h8.12.md) | 2026-10-07 15:52:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3y.grk][1] | Need 1h8 phase statuses that overlap sase-1h5 Beads-pane work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3y.grk/README.md

<!-- sase:referenced-by:end -->

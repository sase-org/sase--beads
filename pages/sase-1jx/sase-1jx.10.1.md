# Bead: sase-1jx.10.1 — Add an existing repository from the New Project wizard

[Bead Pages](../README.md) / [sase-1jx.10](sase-1jx.10.md) / sase-1jx.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.10.md) · **Assignee:** `sase-1jx.10.1.land`
**Created:** 2026-10-12 04:39:46 EDT · **Closed:** 2026-10-12 09:11:17 EDT
**Plan:** [202610/new\_project\_add\_existing.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_add_existing.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/new_project_add_existing.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/new_project_add_existing.md

<!-- sase:links:end -->

## Description

Configure, Review, durable apply, live progress, the shared init hand-off, and Ready or Failed work for an existing repository, and the Projects pane init flow keeps its current behavior. The land agent closes phase bead sase-1jx.10 and does not close epic sase-1jx.

## Notes

[2026-10-12T12:12:29Z · sase-1jx.10.1.land] FOLLOW-UP TRIAGE (completed before the remaining-work tale): sase-1jx.10.1.1 note #1 and sase-1jx.10.1.2 note #1 report the same old stale Symvision rows; declined new tasks because 8ed37c4ef8 privatized journal_path/journal_lock_path/journal_lock and re-keyed archive_read_only_context, and 52e10f302a subsequently retired the archive entry. sase-1jx.10.1.3 note #1 proposes mark_archive_row_restored cleanup; declined because ebd17bf5bf removed its exemption when the Archive gained a real consumer. Current Justfile has none of those rows. sase-1jx.10.1.4 note #1 import budget: corroborated existing task sase-1ic (+1, +10 independent reports) with isolated 3517 < 3513 failure; tools/tui_import_closure --diff 86b8fe2cce^ shows 3518 before this child epic and only one Archive module removed, no wizard growth. Additional independent just symvision failure for _archive_reader._load_archive_bundle imported by _archive_restore.py:169/:177 traces to ebd17bf5bf (sase-1jm.5); searched task duplicates and last-week ci sweep, read active epic sase-1jm and phase sase-1jm.5, and attached DISCOVERED ISSUE to sase-1jm instead of creating a task. All non-epic proposals are triaged; none is remaining New Project work.

[2026-10-12T12:14:34Z · sase-1jx.10.1.land] LANDING AUDIT: read this epic and every note on phases .1-.4, audited both linked plans and parent phase sase-1jx.10, reviewed epic commits 86b8fe2cce/393d0a4a5a/5714395778/558a45eca4 and non-epic commits through 558a45eca4 (including apply split 313492a4f0 and CLI-create 597931b222). Parent decisions honored: no human-only decision record or memory edit; keymap/create entry belongs to .11/.12; private-primary sidecars use existing init. 66 focused models/configure/review/apply/init/modal/producer-inventory tests pass. Inspected all eight Configure/Review/Progress/Failed/Ready goldens, including 80x24 Review. Epic-symbols sase-1jx.10.1 has none. Cannot close: failed resume selects Review with no plan, no draft and zero check submissions; live Configure passes only records and discards even supplied managed/push facts (target can_push=None/sase_managed=None, setup unknown_push); old Review completion overwrites latest plan (newest then obsolete returns obsolete argv), and rejected duplicate submission leaves _loading=True with no view; init terminal reload unconditionally calls _on_init_finished(True) without checking command outcome; Progress re-reads unchanged logs before result and never observes a failed proc with no NDJSON result; render_stepper leaves Review active for Progress/Ready/Failed instead of done. These are epic defects, to be repaired in one medium tale that owns this epic closeout and normal close of parent phase sase-1jx.10.

[2026-10-12T13:11:17Z · sase-1jx.10.1.land] Verified all four original children remain closed (.1-.4). Planner-backed Configure uses Source probe cache plus local inventory facts via plan_configure_display; records-only validate_draft is unchanged. Failed resumes hydrate into a checked Review from journal plus operation request plus proc command without executing stored argv. Review generation+fingerprint dedup rejects duplicate submissions immediately; only the current-generation loading completion enables confirm; back/cancel invalidate checks. Init finishes only from report_init_outcome; wizard terminal nonzero reports False and zero rechecks via start_init_check; pane recheck_after_terminal stays False. Progress honors log.version, stops after a terminal result, observes unsuccessful durable completion without NDJSON, and never synthesizes Ready without identity. Completed-stage chrome: progress/ready/failed stepper marks all three steps done; Configure/Review hints are real; provider cycle stays on Source.

Focused wizard/apply/init/producer tests passed. just fmt passed. Targeted New Project goldens: 8 updated (configure/review/progress/ready/failed chrome), Source pixels unchanged; TZ=UTC just fix-tui-screenshots --check clean 13/13. sase tool run d187e06c403c0c0102e06af161eb25c4 verdict no_new_failures exit 1: 1 KNOWN lint (symvision) private import of _load_archive_bundle from _archive_reader.py (witnesses 0d0e7cc8a4cdd11885a1cc3a085839d9, ac030f72986c6ca65ee05cb614e9257e), already DISCOVERED ISSUE on sase-1jm; fmt/ruff/mypy/scoped tests and remaining lint stages passed. epic-symbols sase-1jx.10.1 empty; Justfile .11(NewProjectModal) and .12(record_visibility_selection) preserved. Follow-up triage retained: stale whitelist notes declined (8ed37c4ef8/52e10f302a/ebd17bf5bf); .4 import budget corroborated sase-1ic; Archive _load_archive_bundle remains sase-1jm. Concurrent HEAD b4dbfcd90e RECORD deck; this tale did not consume record_visibility_selection or wire .11/.12 entry points.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.10.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.10.1.land.md) | [sase-1jx.10.1](sase-1jx.10.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`95e2115`](https://github.com/sase-org/sase/commit/95e2115b16e8524b4d42230b333d11d6edb25199) | fix(tui): land add-existing New Project wizard repairs | [sase-1jx.10.1](sase-1jx.10.1.md) | 2026-10-12 09:14:25 EDT |
| sase--plans | [`sase--plans@81377d5`](https://github.com/sase-org/sase--plans/commit/81377d5c33d16e1bfa7bc40a23719d81ecdc5e98) | docs(plans): mark add-existing New Project epic plan done | [sase-1jx.10.1](sase-1jx.10.1.md) | 2026-10-12 09:18:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.4.2.3][1] | Check whether this known symvision failure is already tracked and has clean-base evidence | 1 |
| read-by | [agent:sase-1jx.10.1.1--1][2] | parent epic decisions for phase work | 1 |
| read-by | [agent:sase-1jx.10.1.2][3] | parent epic scope | 1 |
| read-by | [agent:sase-1jx.10.1.3][4] | Need epic decisions and constraints for the assigned configure-review phase | 1 |
| read-by | [agent:sase-1jx.10.1.4][5] | Need parent epic decisions and full plan scope | 1 |
| read-by | [agent:sase-1jx.11][6] | Verify the existing record for the known Symvision baseline failure | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4.2.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.10.1.1.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10.1.2/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10.1.3/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10.1.4/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.11/README.md

<!-- sase:referenced-by:end -->

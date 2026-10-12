# Bead: sase-1jx.12.1 — Complete repository creation in the New Project wizard

[Bead Pages](../README.md) / [sase-1jx.12](sase-1jx.12.md) / sase-1jx.12.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.12.md) · **Assignee:** `sase-1jx.12.1.land`
**Created:** 2026-10-12 10:07:50 EDT · **Closed:** 2026-10-12 14:20:05 EDT
**Plan:** [202610/create\_repository\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/create_repository_wizard.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/create_repository_wizard.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/create_repository_wizard.md

<!-- sase:links:end -->

## Description

Deliver the provider form, live create checks, danger Review, durable apply, and journal-backed recovery required by sase-1jx.12, then have this child epic's land agent close that phase.

## Notes

[2026-10-12T18:20:05Z · sase-1jx.12.1.land] Verified sase-1jx.12.1 against the child plan, parent phase sase-1jx.12 (tui-create), and the four closed phase notes. Commits 0defe76db8, 3dc675fffe, 1de7cf6c8d, and 241e33a797 implement the provider form, create Configure, danger Review/apply, and recovery plus the pinned Create row. Source review confirms lenient evaluate_repo_creation_form, 300ms off-thread probes, explicit add-instead, project.create durable submit, record_visibility_selection only after successful create (including dismissed-modal completion), mode-aware resume with Back restore, and Source n. Human-only create guard is unchanged. No feature flag and no glossary or human-only decision edits. sase bead epic-symbols sase-1jx.12.1, sase-1jx.12, and sase-1jx are empty; the sase-1jx.12(record_visibility_selection) row is gone. 165 focused create/add/resume/planning/cli/inventory tests passed. Import closure versus 0defe76db8^ is +0 modules.

Integration: non-epic commits since the epic started overlap only styles.tcss, in the Plan Review region, and the create danger rules landed after them. The apply-test split and the archive-pane retirement do not touch the wizard. No duplicate create path to rewire.

Follow-ups: declined _load_archive_bundle and the revival-preview assertion as already fixed (public load_archive_bundle in b249bc5e69; test_custom_search_preview_describes_archive_browsing passes) and noted that on sase-1jm. Declined the sase-1ju rule-7 flag lint because 101c853939 removed agents_archive_view from the flag registry. Corroborated the still-open import-budget failure on sase-1ic (+1; 3517 vs cap 3513, not grown by this epic) and the Project: fake/tmp header failures on sase-1k4 (+1; both tests still fail). Neither is caused by this epic.

[2026-10-12T18:57:51Z · sase-1jx.12.1.land] Post-close cleanup after the 2026-10-12T18:20:05Z close. just symvision was red on test-only publics once this epic closed, so the landing diff privatizes this epic's create/resume helpers (_add_instead_seed, _build_create_plan_request, _create_identity_verdict, _create_review_request, _default_create_owner, _default_create_visibility, _lenient_effective_options, _probe_result_current, _supported_create_visibilities, _ResumeContext, _CreateRecovery) and the other unused publics the recipe still listed (plan-decision cards/rows, archive helpers, _validate_draft, _checkout_facts_from_source, _apply_identity_lock_path). Two create-flow tests used inline pilot.pause loops; both now use sase.ace.testing.wait.wait_for. just symvision then printed that all public/private classes and functions are used properly. Plan plan:202610/create_repository_wizard.md is status done. sase tool run check 33a35cb4c27e1fe5082745a546ca50e2 passed every lint stage, including symvision and test waits, then test (scoped) reported 5 failed / 55353 passed. Those five are pre-existing and not in this diff: the import budget is sase-1ic, the two Project header tests are sase-1k4, and test_dismissed_marker plus test_neighbors_map_shows_dismissed_revive_cells are a DISCOVERED ISSUE on sase-1jm (jump_opens_archive copy still says ▶ archive). The 11 plan-decision symbols are the ready task sase-1kd, closed as done by this diff. No epic-symbol rows remain for sase-1jx.12.1. Parent phase sase-1jx.12 stayed closed. Containing epic sase-1jx stays open.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.12.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12.1.land/README.md) | [sase-1jx.12.1](sase-1jx.12.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5cb48bd`](https://github.com/sase-org/sase/commit/5cb48bdd36933d2512dc0669f71b5a0bf22eaf30) | refactor(ace): privatize test-only symbols after the create wizard | [sase-1jx.12.1](sase-1jx.12.1.md) | 2026-10-12 14:59:57 EDT |
| sase--plans | [`sase--plans@81830f0`](https://github.com/sase-org/sase--plans/commit/81830f0439a5cc16ea72b5a0f11804f656b83599) | docs(plans): mark the create-repository wizard plan done | [sase-1jx.12.1](sase-1jx.12.1.md) | 2026-10-12 15:04:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.12.1.1][1] | Need parent decisions and surrounding wizard scope | 2 |
| read-by | [agent:sase-1jx.12.1.2][2] | parent epic scope | 1 |
| read-by | [agent:sase-1jx.12.1.4--1][3] | need full epic DECISIONS | 2 |
| read-by | [agent:sase-1jx.12.1.land][4] | Need decisions, notes, description, and children status | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12.1.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.12.1.4.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12.1.land/README.md

<!-- sase:referenced-by:end -->

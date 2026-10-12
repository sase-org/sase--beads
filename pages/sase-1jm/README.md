# Bead: sase-1jm — Agents tab Archive view retires Artifacts ▸ Agent

[Bead Pages](../README.md) / sase-1jm

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.45.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.45.linker.w0.md) · **Assignee:** `sase-1jm.land`
**Created:** 2026-10-10 06:41:07 EDT
**Plan:** [202610/agents\_archive\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/agents_archive_view.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1kc][2] | The epic whose glossary decisions were answered no; its plan file is the source of truth for the definitions |

_Plus 12 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1kc/README.md

<!-- sase:links:end -->

## Description

Every agent that ran on this machine can be found and read on the Agents tab. The Inbox stays exactly as it is today. A new Archive view (`,a`) lists dismissed runs by day and opens any of them read-only in the real decks. Restoring is one deliberate `⏎`. Every `agent:` route lands on the Agents tab. The Artifacts ▸ Agent sub-tab is retired behind a sunset flag.

## Notes

[2026-10-11T13:09:08Z · 6p--code] DISCOVERED ISSUE: at master 8122d44255 (also origin/master cca1773157, which only adds the git-lock and symvision-privatize commits), `sase tool run check` fails three tests that this epic's archive work causes. (1) tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift and ::test_current_structural_view_matches_checked_in_snapshot: the only drift is description_digest of `sase agent search` (d0bf3fe5c8158622 current vs f75a3fcb2bbd4075 in tests/completion/snapshots/cli_spec.json), changed by the archive search CLI parity commits (5f47d11935, 04ed4b33cb); regenerate with `just sync-completion-spec`. (2) tests/completion/test_candidates_providers.py::test_flag_candidates_come_from_the_in_process_registry: the in-process flag registry now holds {'agents_archive_view'} while the test asserts it is empty; either register the expectation or let sase-1ju (Retire agents_archive_view) clear it. Found while verifying an unrelated plan-propose change; none of these files were touched by it.

[2026-10-12T06:36:46Z · sase-1jm.3.1.8.land] DISCOVERED ISSUE (sase-1jm.3.1.8 land agent, master 791c1797b9): every AceApp startup imports the Archive modules even with the agents_archive_view beta off. actions/_state_init_runtime.py:init_runtime_state (since 69f647d912, sase-1jm.3.1) calls init_agents_archive_view_state, which imports actions.agents._archive_view, models.agent_archive_view (module-level) and _archive_controller, loads the Archive grouping preference, and initializes the controller. So sase-1jm.3.1.8's static import deferral (both modules are off the sase.ace.tui.app closure) gives no runtime startup saving; a verifier's mounted probe confirmed both modules are in sys.modules after startup. Remediation: lazy-init _agents_archive_view on first Archive access (agents_archive_is_active already tolerates the missing attribute), or skip init entirely while the beta is off, without breaking the Archive prewarm budget (warm ,a < 100 ms). Can wait for the retire-pane phase that removes the beta flag.

[2026-10-12T06:36:51Z · sase-1jm.3.1.8.land] DISCOVERED ISSUE (sase-1jm.3.1.8 land agent, from phase sase-1jm.3.1.8.5 evidence): Archive j/k latency has not been confirmed against the 16 ms p95 budget on a quiet host. Same-host back-to-back runs on loaded athena (load1 11-15): bench_tui_jk_archive p50 ~42 ms, p95 ~47-53 ms over 2 runs; axe bench_tui_jk Inbox control p50 17-56 ms, p95 45-65 ms. That is a loaded-host band, not an Archive regression (Archive is within the control's range). Warm ,a first-row median 99.6 ms passes the 100 ms budget. Re-measure both benches back to back on a quiet host before sase-1jm retires the beta flag; related host-load reports: sase-1ge, sase-199.

[2026-10-12T12:11:38Z · sase-1jx.10.1.land] DISCOVERED ISSUE: sase-1jx.10.1 land review at master 558a45eca4 reproduces just symvision failure: private _load_archive_bundle in src/sase/ace/tui/actions/agents/_archive_reader.py is imported by non-test _archive_restore.py:169 and called at :177, added in ebd17bf5bf (sase-1jm.5). No task duplicates found by ci/all-type searches for _load_archive_bundle or archive_reader and the last-week ci task sweep. Archive epic remains active; wire a supported public entry with its real consumer or remove the cross-file private import per symvision policy. Not caused by New Project.

[2026-10-12T15:21:23Z · sase-1jm.4.2.land] DISCOVERED ISSUE (sase-1jm.4.2 land agent, master ee673ce10d): tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py::test_archive_help_png_snapshot fails: after scrolling the Agents help modal until 'Live actions stay in Inbox' paints, assert_page_svg_contains(page, 'Archive (read-only)') fails because the box title has scrolled off. Bisected with TZ=UTC pytest -m visual: passes at ebd17bf5bf~1, fails at ebd17bf5bf (sase-1jm.5, which added 5 rows to help_modal/agents_archive_sections.py); golden agents_archive_help_120x40.png last updated at 8270bf768f. Fix the scroll stop condition (stop once the title row is visible, or scroll the box into view) and rebaseline the golden. Proposed by phase sase-1jm.4.2.4 (note #3); no task duplicate found.

[2026-10-12T15:21:28Z · sase-1jm.4.2.land] DISCOVERED ISSUE (sase-1jm.4.2 land agent, master ee673ce10d): tests/ace/tui/modals/test_saved_agent_group_revival_rendering.py::test_custom_search_preview_describes_recent_unscoped_filtering fails: it asserts '250 most recent dismissed agents' but the preview now reads 'Custom revival search / Load recent dismissed agents, then filter and choose their scope.' The copy changed in c4c7846f57 (sase-1jm.6, route agent arrivals to Archive), which did not update the test. Update the assertion to the new Archive-aware copy (both agents_archive_view on/off branches). Proposed by phase sase-1jm.4.2.2 (note #3); no task duplicate found.

[2026-10-12T15:21:32Z · sase-1jm.4.2.land] DISCOVERED ISSUE (sase-1jm.4.2 land agent): resolve_archive_bundle_path (models/agent_archive_reader.py:158) first checks row.get('bundle_path'), but the Rust AgentArchiveLightRowWire (sase-core agent_archive/corpus/wire.rs, serde deny_unknown_fields) has no bundle_path (nor raw_suffix/stop_time), so that branch is dead for real rows and every hydration falls back to the <source_run_id>.json root scan; only test fixtures pass bundle_path. Either carry bundle_path on the light row through sase-core or drop the dead branch. Record's record_subject_from_light_row reads the same absent keys and degrades soft (no Bundle/Dismissed facts on unreadable entries). Raised by the sase-1jm.4.2 plan landing section; no task duplicate found.

[2026-10-12T15:47:46Z · sase-1ka.land] DISCOVERED ISSUE corroboration (sase-1ka land agent): both existing sase-1jm DISCOVERED ISSUEs still reproduce on master c9c1df82cc and were independently proposed by sase-1ka phases: (1) Symvision private import of _load_archive_bundle (_archive_restore.py:169 -> _archive_reader.py:304, from sase-1jm.5 ebd17bf5bf) was flagged KNOWN by sase-1ka.2, sase-1ka.4, and sase-1ka.5; (2) test_custom_search_preview_describes_recent_unscoped_filtering still asserts '250 most recent dismissed agents' after c4c7846f57 (sase-1jm.6) changed the copy to 'Load recent dismissed agents...' (proposed by sase-1ka.3). Both remain sase-1jm landing work; no separate task created.

[2026-10-12T18:18:23Z · sase-1jx.12.1.land] LANDING CHECK from sase-1jx.12.1 at master 101c853939: two earlier DISCOVERED ISSUEs no longer reproduce. The cross-file private import of _load_archive_bundle is gone; production callers use public load_archive_bundle in src/sase/ace/tui/actions/agents/_archive_reader.py (b249bc5e69). tests/ace/tui/modals/test_saved_agent_group_revival_rendering.py::test_custom_search_preview_describes_archive_browsing passes and asserts Archive copy (Browse the Archive / Press Enter on a run), not the old '250 most recent dismissed agents' string. Proposed by sase-1jx.12.1.1, sase-1jx.12.1.2, and sase-1jx.12.1.3; declined as already fixed.

[2026-10-12T18:47:08Z · sase-1jm.land] LAND TRIAGE (sase-1jm.land, master 101c853939) of every PROPOSED FOLLOW-UP on phases .1-.8 (nested child epics .2.1, .3.1, .3.1.8, .4.2 were triaged by their own landers and not redone).

(1) Glossary, from .2 #1/#2, .3 #1/#2/#3, .4 #1/#2, .5 #1/#2, .7 #1/#2, .8 #1/#2: CREATED memory task sase-1kc. It adds glossary:agent-archive and updates nav-section, nav-item, agent-data-deck, and agent-relation-jump-target. It has a related link to sase-1c9, which also edits agent-data-deck. The epic's decisions forbid memory edits, so this stays out of the epic.
(2) .1 #2, closed-flag residue for sase-18l/sase-1ar: DECLINED. tools/check_feature_flags exits 0 at 101c853939.
(3) .3 #4, agents_unified_query matrix: DECLINED. The flag was retired by b46ecb0a94 before this epic, as sase-1jm.3.1.land also concluded.
(4) .3 #5, clean-base failures: DECLINED as already triaged by sase-1jm.3.1.land. tests/completion passes at 101c853939, and the import budget belongs to sase-1ic.
(5) .4 #4, test_usage_limit_e2e: DECLINED. tests/fakey/test_usage_limit_e2e.py passes at 101c853939.
(6) .5 #3, .6 #1, .7 #3, stale Justfile --epic-symbol rows (sase-1jm.3.1, sase-1jx.7.1, sase-1jm.4.1.3, sase-1jm.5, sase-1jx.8): DECLINED. Those rows are gone, and only sase-1jm(archive_corpus_is_warm) remains, which is epic work. The recurring mechanism is tracked by sase-o7.
(7) .5 #4 and .8 #4/#5/#6/#8, KNOWN failures: already tracked. The import budget is sase-1ic. The Project: fake/tmp header and workflow snapshot tests are sase-1k4, already +1'd with isolated repros by sase-1jm.4.2.land. No new +1 or bead.
(8) .7 #4, full-scope visual drift (155 updated plus 3 missing word-definition goldens): DECLINED. All four word_definition_modal_* goldens exist at 101c853939. The 155-update count kept no report, SHA, or node list, so it is not actionable; CI's visual-test job is the oracle. This epic's own goldens are rechecked by the remaining-work epic.
(9) .8 #3, build_create_plan_request symvision: routed as a DISCOVERED ISSUE note on the active epic sase-1jx. The note also covers 13 sibling New Project unused publics.
(10) .8 #7, retired Artifacts strip and toast goldens: EPIC WORK, planned.
Also found: symvision now reports unused publics that b249bc5e69 un-masked when it removed the private import that made symvision exit early. That set includes sase-1ka's 11 plan decision-card symbols, so I CREATED ci task sase-1kd (closed owner, related to sase-1hp). The 6 symbols caused by this epic (archive_corpus_is_warm, archive_name_query, convert_agents_pane_query, load_archive_name_candidates, sync_archive_shelf, ArtifactLinkGroup) are epic work.
Epic DISCOVERED ISSUEs: #1 is resolved (completion tests pass), and #4/#6 are resolved per note #9. #2 (eager startup grouping read), #3 (quiet-host j/k), #5 (Archive help PNG), and #7 (light-row bundle_path) are epic work, planned in a child epic.

[2026-10-12T18:57:33Z · sase

… and 1320 more characters

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1jm.1](sase-1jm.1.md) | Archive index v3 and honest timestamps | ✓ closed | medium | 2026-10-10 | 1 | 1 |
| [sase-1jm.2](sase-1jm.2.md) | Core archive corpus, in scope token, and CLI parity | ✓ closed | large | 2026-10-10 | 1 | 0 |
| [sase-1jm.3](sase-1jm.3.md) | Archive view on the Agents tab | ✓ closed | large | 2026-10-10 | 1 | 0 |
| [sase-1jm.4](sase-1jm.4.md) | Record deck for every agent | ✓ closed | medium | 2026-10-10 | 1 | 1 |
| [sase-1jm.5](sase-1jm.5.md) | Restore, fork, and copy from the Archive | ✓ closed | medium | 2026-10-10 | 1 | 1 |
| [sase-1jm.6](sase-1jm.6.md) | Every agent route lands on the Agents tab | ✓ closed | medium | 2026-10-10 | 1 | 1 |
| [sase-1jm.7](sase-1jm.7.md) | Inbox shelf, zero-result bridge, and Node Finder matches | ✓ closed | medium | 2026-10-10 | 1 | 1 |
| [sase-1jm.8](sase-1jm.8.md) | Retire Artifacts ▸ Agent and make the Archive unconditional | ✓ closed | medium | 2026-10-10 | 1 | 1 |

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.1/README.md) | [sase-1jm.1](sase-1jm.1.md) | 1 |
| [bbugyi200.athena.sase-1jm.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.2.md) | [sase-1jm.2](sase-1jm.2.md) | 0 |
| [bbugyi200.athena.sase-1jm.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.1/README.md) | [sase-1jm.2.1.1](sase-1jm.2.1.1.md) | 2 |
| [bbugyi200.athena.sase-1jm.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.2/README.md) | [sase-1jm.2.1.2](sase-1jm.2.1.2.md) | 1 |
| [bbugyi200.athena.sase-1jm.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.3/README.md) | [sase-1jm.2.1.3](sase-1jm.2.1.3.md) | 1 |
| [bbugyi200.athena.sase-1jm.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.4/README.md) | [sase-1jm.2.1.4](sase-1jm.2.1.4.md) | 1 |
| [bbugyi200.athena.sase-1jm.2.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.5/README.md) | [sase-1jm.2.1.5](sase-1jm.2.1.5.md) | 2 |
| [bbugyi200.athena.sase-1jm.2.1.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.2.1.6.md) | [sase-1jm.2.1.6](sase-1jm.2.1.6.md) | 1 |
| [bbugyi200.athena.sase-1jm.2.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.2.1.land.md) | [sase-1jm.2.1](sase-1jm.2.1.md) | 2 |
| [bbugyi200.athena.sase-1jm.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.md) | [sase-1jm.3](sase-1jm.3.md) | 0 |
| [bbugyi200.athena.sase-1jm.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.1/README.md) | [sase-1jm.3.1.1](sase-1jm.3.1.1.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.2/README.md) | [sase-1jm.3.1.2](sase-1jm.3.1.2.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.3/README.md) | [sase-1jm.3.1.3](sase-1jm.3.1.3.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.4/README.md) | [sase-1jm.3.1.4](sase-1jm.3.1.4.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.5/README.md) | [sase-1jm.3.1.5](sase-1jm.3.1.5.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.6/README.md) | [sase-1jm.3.1.6](sase-1jm.3.1.6.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.7.md) | [sase-1jm.3.1.7](sase-1jm.3.1.7.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.1/README.md) | [sase-1jm.3.1.8.1](sase-1jm.3.1.8.1.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.8.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.8.2.md) | [sase-1jm.3.1.8.2](sase-1jm.3.1.8.2.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.3/README.md) | [sase-1jm.3.1.8.3](sase-1jm.3.1.8.3.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.4/README.md) | [sase-1jm.3.1.8.4](sase-1jm.3.1.8.4.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.5/README.md) | [sase-1jm.3.1.8.5](sase-1jm.3.1.8.5.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.8.land.md) | [sase-1jm.3.1.8](sase-1jm.3.1.8.md) | 1 |
| [bbugyi200.athena.sase-1jm.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.land.md) | [sase-1jm.3.1](sase-1jm.3.1.md) | 0 |
| [bbugyi200.athena.sase-1jm.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4/README.md) | [sase-1jm.4](sase-1jm.4.md) | 1 |
| [bbugyi200.athena.sase-1jm.4.2.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.4.2.1.md) | [sase-1jm.4.2.1](sase-1jm.4.2.1.md) | 1 |
| [bbugyi200.athena.sase-1jm.4.2.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4.2.2/README.md) | [sase-1jm.4.2.2](sase-1jm.4.2.2.md) | 1 |
| [bbugyi200.athena.sase-1jm.4.2.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4.2.3/README.md) | [sase-1jm.4.2.3](sase-1jm.4.2.3.md) | 1 |
| [bbugyi200.athena.sase-1jm.4.2.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4.2.4/README.md) | [sase-1jm.4.2.4](sase-1jm.4.2.4.md) | 1 |
| [bbugyi200.athena.sase-1jm.4.2.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4.2.5/README.md) | [sase-1jm.4.2.5](sase-1jm.4.2.5.md) | 1 |
| [bbugyi200.athena.sase-1jm.4.2.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.4.2.land.md) | [sase-1jm.4.2](sase-1jm.4.2.md) | 2 |
| [bbugyi200.athena.sase-1jm.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.5.md) | [sase-1jm.5](sase-1jm.5.md) | 1 |
| [bbugyi200.athena.sase-1jm.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.6/README.md) | [sase-1jm.6](sase-1jm.6.md) | 1 |
| [bbugyi200.athena.sase-1jm.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.7/README.md) | [sase-1jm.7](sase-1jm.7.md) | 1 |
| [bbugyi200.athena.sase-1jm.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.8/README.md) | [sase-1jm.8](sase-1jm.8.md) | 1 |
| [bbugyi200.athena.sase-1jm.9.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.9.1.md) | [sase-1jm.9.1](sase-1jm.9.1.md) | 1 |
| [bbugyi200.athena.sase-1jm.9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.2/README.md) | [sase-1jm.9.2](sase-1jm.9.2.md) | 0 |
| [bbugyi200.athena.sase-1jm.9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.3/README.md) | [sase-1jm.9.3](sase-1jm.9.3.md) | 0 |
| [bbugyi200.athena.sase-1jm.9.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.4/README.md) | [sase-1jm.9.4](sase-1jm.9.4.md) | 0 |
| [bbugyi200.athena.sase-1jm.9.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.5/README.md) | [sase-1jm.9.5](sase-1jm.9.5.md) | 0 |
| [bbugyi200.athena.sase-1jm.9.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.6/README.md) | [sase-1jm.9.6](sase-1jm.9.6.md) | 0 |
| [bbugyi200.athena.sase-1jm.9.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.7/README.md) | [sase-1jm.9.7](sase-1jm.9.7.md) | 0 |
| [bbugyi200.athena.sase-1jm.9.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.8/README.md) | [sase-1jm.9.8](sase-1jm.9.8.md) | 0 |
| [bbugyi200.athena.sase-1jm.9.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.land/README.md) | [sase-1jm.9](sase-1jm.9.md) | 0 |
| [bbugyi200.athena.sase-1jm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.land.md) | [sase-1jm](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e200cf6`](https://github.com/sase-org/sase/commit/e200cf6d677fcb6473d070d6a9a800f088eac3e6) | feat(agents): add v3 dismissed archive index | [sase-1jm.1](sase-1jm.1.md) | 2026-10-10 07:06:42 EDT |
| sase-core | [`sase-core@9f6ce0c`](https://github.com/sase-org/sase-core/commit/9f6ce0c63e6d4694055e8aa195c331e6db138f6d) | feat(agent-archive): add live status-bucket match with outcome derived from bucket | [sase-1jm.2.1.1](sase-1jm.2.1.1.md) | 2026-10-10 10:12:47 EDT |
| sase | [`166289a`](https://github.com/sase-org/sase/commit/166289ac43de125720807da2c935af04c2470311) | feat(agent): add status\_bucket\_for\_values thin wrapper over Rust status bucket binding | [sase-1jm.2.1.1](sase-1jm.2.1.1.md) | 2026-10-10 11:22:40 EDT |
| sase | [`18f53d3`](https://github.com/sase-org/sase/commit/18f53d3e57626ac868975005e6d0fb4e720c09ab) | feat(query): add agents-archive profile and host-owned in: token | [sase-1jm.2.1.4](sase-1jm.2.1.4.md) | 2026-10-10 11:40:40 EDT |
| sase-core | [`sase-core@e4e72c2`](https://github.com/sase-org/sase-core/commit/e4e72c2a357b230d16af0aecbfdef389213cc7de) | feat(archive): compile v3 archive corpus | [sase-1jm.2.1.2](sase-1jm.2.1.2.md) | 2026-10-10 12:34:13 EDT |
| sase-core | [`sase-core@431599f`](https://github.com/sase-org/sase-core/commit/431599f402c3167b499a2bdc0d20a693558e54bb) | feat(archive): query compiled corpus for summary, rows, lookup, and count | [sase-1jm.2.1.3](sase-1jm.2.1.3.md) | 2026-10-10 13:49:40 EDT |
| sase-core | [`sase-core@bc40675`](https://github.com/sase-org/sase-core/commit/bc40675233d35f370e7bf915ddda170e695abf04) | feat(archive): bind corpus compile, summary, rows, lookup, and count | [sase-1jm.2.1.5](sase-1jm.2.1.5.md) | 2026-10-10 15:20:15 EDT |
| sase | [`f7026aa`](https://github.com/sase-org/sase/commit/f7026aa2f2d6a1bd5b3858ed10282e2c7d2fe748) | feat(archive): add AgentArchiveCorpus facade and shared TUI/CLI cache | [sase-1jm.2.1.5](sase-1jm.2.1.5.md) | 2026-10-10 15:25:29 EDT |
| sase | [`5f47d11`](https://github.com/sase-org/sase/commit/5f47d119356f02a87ec850aba52c6bd5090bd365) | feat(agents): add archive search CLI parity | [sase-1jm.2.1.6](sase-1jm.2.1.6.md) | 2026-10-10 16:04:53 EDT |
| sase-core | [`sase-core@cd2a72e`](https://github.com/sase-org/sase-core/commit/cd2a72eda5e92ee838f2567246db8b4f99e33ae9) | feat(archive): keep compiled corpus in Rust and resolve child owners | [sase-1jm.2.1](sase-1jm.2.1.md) | 2026-10-10 20:12:05 EDT |
| sase | [`69f647d`](https://github.com/sase-org/sase/commit/69f647d9125f3014b7aa38629fc59963af098544) | feat(agents-archive): add Archive view state, flag, and selection ownership | [sase-1jm.3.1.1](sase-1jm.3.1.1.md) | 2026-10-10 20:46:00 EDT |
| sase | [`04ed4b3`](https://github.com/sase-org/sase/commit/04ed4b33cbd426c34c8282aef702dc261e6bee45) | feat(archive): query the Rust-held corpus handle from the facade and CLI | [sase-1jm.2.1](sase-1jm.2.1.md) | 2026-10-10 21:12:36 EDT |
| sase | [`254d93c`](https://github.com/sase-org/sase/commit/254d93cc5808b7f12850027883a7be86c64ef195) | feat(tui): add pump-free Archive corpus controller | [sase-1jm.3.1.2](sase-1jm.3.1.2.md) | 2026-10-10 23:06:31 EDT |
| sase | [`b6acacf`](https://github.com/sase-org/sase/commit/b6acacfa082643fa298e217b9159256acc40b5ba) | feat(tui): add paged Archive list column and live Inbox pulse | [sase-1jm.3.1.3](sase-1jm.3.1.3.md) | 2026-10-11 01:08:10 EDT |
| sase | [`5349e04`](https://github.com/sase-org/sase/commit/5349e046cdad8356bc382d65f87f30f910cb777b) | feat(ace): add Agents Archive view | [sase-1jm.3.1.4](sase-1jm.3.1.4.md) | 2026-10-11 02:03:39 EDT |
| sase--plans | [`sase--plans@109c5ff`](https://github.com/sase-org/sase--plans/commit/109c5ff3f8b22923618a2ac8226aa836dc2837fe) | feat(plans): add record-deck child epic plan for sase-1jm.4 | [sase-1jm.4](sase-1jm.4.md) | 2026-10-11 05:32:31 EDT |
| sase | [`7ad439f`](https://github.com/sase-org/sase/commit/7ad439fd42dc6615321b05a5d64320a13cfebe4a) | feat(tui): hydrate archived agent detail off-thread as read-only | [sase-1jm.3.1.5](sase-1jm.3.1.5.md) | 2026-10-11 12:45:41 EDT |
| sase | [`4841439`](https://github.com/sase-org/sase/commit/4841439aeed3e217ec0e3c7037786ddb5c8fd7eb) | feat(agents): isolate Archive action boundary with read-only guards | [sase-1jm.3.1.6](sase-1jm.3.1.6.md) | 2026-10-11 16:08:20 EDT |
| sase | [`11e73e8`](https://github.com/sase-org/sase/commit/11e73e82325a3506489419bec9bcabc45a2dc194) | feat(agents-archive): proof coverage, benchmarks, and PNG goldens with test-wait lint fixes | [sase-1jm.3.1.7](sase-1jm.3.1.7.md) | 2026-10-11 18:30:07 EDT |
| sase | [`1b837fa`](https://github.com/sase-org/sase/commit/1b837fa132e932f6cdf319e86649689980e436bb) | refactor(agents): consolidate archive detail ownership into dedicated modules | [sase-1jm.3.1.8.1](sase-1jm.3.1.8.1.md) | 2026-10-11 20:16:47 EDT |
| sase | [`fb46ff6`](https://github.com/sase-org/sase/commit/fb46ff6f72a0b8b567ea10cf3504977f039f9062) | fix(tui): harden Archive controller seams and show project names | [sase-1jm.3.1.8.2](sase-1jm.3.1.8.2.md) | 2026-10-11 21:35:54 EDT |
| sase | [`8270bf7`](https://github.com/sase-org/sase/commit/8270bf768fed558909db3ef5371bca298cecd42f) | fix(tui): keep Archive actions read-only | [sase-1jm.3.1.8.3](sase-1jm.3.1.8.3.md) | 2026-10-11 22:38:57 EDT |
| sase | [`273d6f0`](https://github.com/sase-org/sase/commit/273d6f0d9bc38b9ebeb96eba4bf2dfe9d33cd104) | feat(tui): park Archive views and defer Archive imports | [sase-1jm.3.1.8.4](sase-1jm.3.1.8.4.md) | 2026-10-12 00:45:48 EDT |
| sase | [`17010f2`](https://github.com/sase-org/sase/commit/17010f2c6e8e3fda0482e70be075a3d4e1ffc900) | test(tui): add Archive remaining-proof regressions and marked/restored goldens | [sase-1jm.3.1.8.5](sase-1jm.3.1.8.5.md) | 2026-10-12 02:02:03 EDT |
| sase | [`c4c7846`](https://github.com/sase-org/sase/commit/c4c7846f57dfee7c054b0ce71fe8d7b039521670) | feat(ace): route agent arrivals to Archive | [sase-1jm.6](sase-1jm.6.md) | 2026-10-12 04:32:15 EDT |
| sase | [`83ed7d7`](https://github.com/sase-org/sase/commit/83ed7d7082c2959139c971b52820f2fc7ac81398) | fix(ace): finish Agents Archive landing defects before sase-1jm.3.1 lands | [sase-1jm.3.1.8](sase-1jm.3.1.8.md) | 2026-10-12 05:49:02 EDT |
| sase | [`ebd17bf`](https://github.com/sase-org/sase/commit/ebd17bf5bf64b1d9cb8dfa5001fc880c99dfb603) | feat(agents-archive): add restore, fork, and copy actions to the Archive | [sase-1jm.5](sase-1jm.5.md) | 2026-10-12 06:06:46 EDT |
| sase | [`db32983`](https://github.com/sase-org/sase/commit/db32983ba23026b9b61ca850493e37c8ae8cd007) | feat(ace): add Archive entry points to agent navigation | [sase-1jm.7](sase-1jm.7.md) | 2026-10-12 07:01:26 EDT |
| sase | [`b4dbfcd`](https://github.com/sase-org/sase/commit/b4dbfcd90e7d38654b2535c87a7008f7b686feb2) | feat(ace-tui): add RECORD deck with picker, split-rails and Archive views | [sase-1jm.4.2.1](sase-1jm.4.2.1.md) | 2026-10-12 08:15:39 EDT |
| sase | [`e82db58`](https://github.com/sase-org/sase/commit/e82db580a2d9b997a50bdd53ee01186c1eaa2954) | feat(ace): add Record relations and links | [sase-1jm.4.2.3](sase-1jm.4.2.3.md) | 2026-10-12 09:07:20 EDT |
| sase | [`a6df5da`](https://github.com/sase-org/sase/commit/a6df5daa01832899da32841bd8f488eb854dadbe) | feat(tui): fill Record Lifecycle and Provenance cards | [sase-1jm.4.2.2](sase-1jm.4.2.2.md) | 2026-10-12 09:23:00 EDT |
| sase | [`f26ac18`](https://github.com/sase-org/sase/commit/f26ac18475c440dca92ec03a76ccde5259c6a67d) | feat(tui): paint Record from Archive light rows | [sase-1jm.4.2.4](sase-1jm.4.2.4.md) | 2026-10-12 10:23:00 EDT |
| sase | [`ee673ce`](https://github.com/sase-org/sase/commit/ee673ce10dea934e14e910d522bc7a8b7051d2b2) | feat(ace): add Record deck PNG goldens, docs, and j/k bench evidence | [sase-1jm.4.2.5](sase-1jm.4.2.5.md) | 2026-10-12 11:03:13 EDT |
| sase | [`5ba61b4`](https://github.com/sase-org/sase/commit/5ba61b41a8b5de3e3146ee5d06517febe06e665d) | fix(ace): finish Record deck landing fixes | [sase-1jm.4.2](sase-1jm.4.2.md) | 2026-10-12 12:16:44 EDT |
| sase--plans | [`sase--plans@9d2f3be`](https://github.com/sase-org/sase--plans/commit/9d2f3bef5249d1969597bce58c9109f5bffc92bc) | docs(plan): mark Record deck refresh complete | [sase-1jm.4.2](sase-1jm.4.2.md) | 2026-10-12 12:21:32 EDT |
| sase | [`101c853`](https://github.com/sase-org/sase/commit/101c8539399669c266d76c01f44ed1e56b24a814) | feat(ace): retire Artifacts Agent pane and make Agent Archive unconditional | [sase-1jm.8](sase-1jm.8.md) | 2026-10-12 14:08:42 EDT |
| sase | [`ba89d2a`](https://github.com/sase-org/sase/commit/ba89d2a6db883a677c6ea0b4e2c784150a1d4ac1) | refactor(ace): remove Archive flag residue and lazy-load grouping | [sase-1jm.9.1](sase-1jm.9.1.md) | 2026-10-12 17:27:12 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:6p--code][1] | Need the epic scope for archive work that registers the agents_archive_view flag | 1 |
| read-by | [agent:sase-1jm.1][2] | Find the epic design and confirm phase notes and linked plan references | 1 |
| read-by | [agent:sase-1jm.2.1.2][3] | Need the epic decisions and phase constraints | 1 |
| read-by | [agent:sase-1jm.2.1.5][4] | Need epic DECISIONS for phase work | 1 |
| read-by | [agent:sase-1jm.3.1.1][5] | Need epic decisions | 1 |
| read-by | [agent:sase-1jm.4.2.3][6] | Check the existing epic record for this pre-existing symvision issue before adding phase follow-up notes | 1 |
| read-by | [agent:sase-1jm.4.2.land--1][7] | Confirm the root epic remains open after closing its Record phase | 1 |
| read-by | [agent:sase-1jm.6][8] | Need the active epic scope related to the stale symbol whitelist failure | 1 |
| read-by | [agent:sase-1jm.7][9] | Need parent epic status, notes, and sibling phase progress | 1 |
| read-by | [agent:sase-1jm.8][10] | Need epic DECISIONS and scope for phase sase-1jm.8 | 1 |
| read-by | [agent:sase-1jx.12.1.1][11] | Need existing work items and notes tracking this KNOWN Symvision issue | 1 |
| read-by | [agent:sase-1jx.12.1.land][12] | See if revival-preview and archive-import issues are already on this epic | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.6p.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.2/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.5/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.1/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4.2.3/README.md
[7]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.4.2.land.md
[8]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.6/README.md
[9]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.7/README.md
[10]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.8/README.md
[11]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12.1.1/README.md
[12]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12.1.land/README.md

<!-- sase:referenced-by:end -->

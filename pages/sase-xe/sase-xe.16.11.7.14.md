# Bead: sase-xe.16.11.7.14 — Stop serving and rendering stale remote fleet rows

[Bead Pages](../README.md) / [sase-xe.16.11.7](sase-xe.16.11.7.md) / sase-xe.16.11.7.14

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0it](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0it.md) · **Assignee:** `sase-xe.16.11.7.14.land`
**Created:** 2026-09-10 13:39:02 EDT
**Plan:** [202609/fleet\_stale\_remote\_rows.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_stale_remote_rows.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/fleet_stale_remote_rows.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/fleet_stale_remote_rows.md

<!-- sase:links:end -->

## Description

A machine's fleet API serves only the agents its own Agents list would present, with honest freshness and liveness, and viewers render honest statuses and authoritative counts - so a cleaned-up remote machine shows clean everywhere.

## Notes

[2026-09-10T20:44:41Z · sase-z7.land] DISCOVERED ISSUE: this epic's landed core half already changed federation normalization, but the SASE-side callers/fixtures were not adopted, so 10 fleet tests fail on clean master for any agent whose sase_core_rs is a dev build from the pinned core revision. Reproduced 2026-09-10 at SASE master HEAD 1ef9c092e with a locally built sase_core_rs from sase-core 93281c3 (workspace sase_16): tests/ace/tui/test_fleet_agents.py (7 nodes) and tests/ace/tui/test_agents_fleet_refresh_laziness.py (3 nodes) fail, e.g. test_offline_fleet_fixture_projects_rows_counts_and_diagnostics asserts len(projection.fleet_rows) == 1 and gets 0; the diagnostics payload shows the host envelope surviving with 'partial': True and 'observed_at_unix': None while every summary is dropped. Reproduces in isolation with -p no:randomly, so it is not a parallel-lane flake. Path: sase.ace.tui.models._fleet_agents_payload.host_payloads -> sase.dispatch.counts.normalize_fleet_federation_response -> Rust fleet_normalize_federation_response, changed by core commit 270e50168391 (phase sase-xe.16.11.7.14.1, 'feat(fleet): bound owner-side presentation and derive honest freshness'). It became live for local dev builds when the sase-za land agent ratcheted sase-core-revision.txt from 161206bac to 270e50168391 in SASE commit 1bfd9f0a1 for an unrelated reason (notification compaction). Published sase-core-rs 0.33.0 predates 270e501, so CI on the published wheel does not see this yet - it will the moment the floor is ratcheted. Phases sase-xe.16.11.7.14.3 (publish and adopt the new core surface) and .4 (liveness-aware rendering) are the open work this belongs to; tests/ace/tui/fleet_fixture.py needs observed_at/freshness that the new normalizer accepts, or the normalizer needs to keep unobserved summaries presentable. Found by the sase-z7 land agent while verifying epic sase-z7; sase-z7 touches no fleet or dispatch code.

[2026-09-10T23:56:40Z · sase-xe.16.11.7.14.land] LANDING AUDIT (2026-09-10): NOT COMPLETE. Reviewed this epic's own note, all five child beads and every child note (nine total), its linked plan, the SASE epic commits f22339c18/cef3ea98d, core commits 270e501/70df126/93281c3, actual current implementations, and every commit/path since epic creation. Audit baseline: SASE 2dcd6a136 and core e0f105d. Durable detailed evidence: file:explicit:e2c64521530457f9913aa9aa (minted and verified exact/live; explicit bead attachment failed in the known artifact-link publisher issue, so the ref is preserved here).

Delivered source includes bounded owner presentation, dismissal lineage lookup/reconciliation, age-based snapshot rebuilding, liveness-aware buckets/counts, adapters, and exception logs. Remaining acceptance is materially incomplete:
1. A two-line raw_prompt_snippet reproduces ValueError: intent must not contain control characters. Phase .5 observed the corresponding Apollo hello/summary HTTP 400 and explicitly could not verify presentation, dismissal propagation, or restart resilience. Attribution correction: git -S locates intent_for_record's introduction at ee7163e, not 270e501. It remains required work because it blocks this epic's live gate.
2. Reproduced merge_catalog_pages against current SASE source: same store generation with sequence 1 rows=[removed], then sequence 2 rows=[current], retains both rows; a late old generation replaces current rows. The event-store generation is not a per-build snapshot identity. Safe snapshot continuation and ordering need completion.
3. The default include_terminal=True is bounded only because the snapshot vector excludes older rows. Catalog pages select only that vector, so the comment claiming cursor continuation reaches older history is false. Complete explicit history reachability and bounded default scope inside this epic.
4. Reproduced a known WAITING-only host rendering 1 agent / 1 unknown: the new banner invents unknown as total-running. The row projection also does not consume new family_role/parent_timestamp, does not feed connection health into status, and assigns host rather than preferred row observation time. Integrate with current machine/status subgroups and the newly landed agents-live role query adapter, and add the missing stale/WAS RUNNING visual acceptance.
5. Reproduced the correlated fixture mutation row_kind=monitor retaining family_role=root failing the new validator. The shared helper actually projects through core; the proposal's missing-field diagnosis is incomplete. This is this epic's contract-integration work. The ACE family_role repair survived the later fixture split; the epic's own ten-node failure note still requires a green combined-tree rerun.
6. Normal unloaded-member dismissal needs a real production-path proof. The reconciliation deadness helper accepts done markers before checking protection and otherwise skips retained PID/running markers without liveness resolution. Ensure live/Unknown/waiting/question protection and dead-active reconciliation; prove dry-run/apply/idempotence and persistence. ACE sync wrappers log exceptions but still ignore False results from an adapter that absorbs ordinary index errors.
7. Phase .3 did not publish/adopt a repaired wheel: PyPI latest remains 0.33.0 from before this epic; pyproject still declares >=0.33.0,<0.34.0. Latest core Release-plz run 34543186306 on e0f105d fails packaging because its generated core_py manifest has no sase_gateway version requirement despite 93281c3's local Cargo.toml fix. The original .3 close reason disclaims verification. Phase .5 used development builds and its own note disclaims the actual live acceptance.

INTEGRATION: Reviewed 28 SASE commits since 13:39 EDT and core drift since the first fleet commit. Relevant work is the fleet fixture split 8d9f24833, machine-status subgroups 4a862d6ea, agents-live adapter bfcdc0416, list/machines helper splits 16001bb36/93789035b, capacity PNG refresh 3e39ebdce, lineage/schema-27 adoption 3260f6a42/core120556a, and pin changes 1bfd9f0a1/3e32c5cc6. Preserve newer artifact-link binding requirements through SASE2dcd6a136/coree0f105d when ratcheting; current pin is da0a738. Remaining provider/pager/notification/runner-slot/usage commits present no further direct fleet adoption requirement from their changed paths.

ALL FIVE PROPOSED FOLLOW-UP OUTCOMES, to retain in the eventual close note:
- .1 #1 Python shared-library path: corroborated existing READY small bug sase-xv, now +4. This landing adds source/impact evidence; .3 already supplied runtime reproduction. No new task.
- .2 #1 link_events registry lint: routed the proposing bead's report to active causal epic sase-yy.8, whose .8.5 owns flag-retirement acceptance. No new task or flag mutation.
- .4 #1 include_terminal ambiguity: declined as an unrelated task; complete default/history contract here.
- .4 #2 family-role fixture: declined as an unrelated task; direct new-contract integration here.
- .5 #1 multiline intent: retained as required live-acceptance repair, with introducing-commit attribution corrected above.
Duplicate searches, recent bug/CI sweep, all 40 active epic scopes, and plausible children were reviewed via /sase_new_task. No new task warranted.

VERIFICATION LIMIT: no full suite run or source edits in this audit. The checkout .venv has an editable core package with no extension; direct probes used current SASE source plus the installed development binding, not a verified PyPI wheel. Remaining phases must restore builds, run full core including PyO3 and SASE just check-full via monitor, and complete the visual/live gates. epic-symbols for this epic is currently clean, but must be rerun when landing resumes.

HANDOFF: authored and validated sase_plan_fleet_remaining_acceptance.md as a child epic with parent_bead=sase-xe.16.11.7.14. Six dependency-ordered phases cover payload/fixtures, dismissal, catalog snapshots/history, real published builds, viewer integration, and live acceptance. Parent close, post-close symvision, and parent plan status are deliberately absent from child phases; the parent link resumes this landing. This epic, its original plan, and every ancestor remain open until the actual work is complete.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.14.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.11.7.14.land.md) | [sase-xe.16.11.7.14](sase-xe.16.11.7.14.md) | 0 |

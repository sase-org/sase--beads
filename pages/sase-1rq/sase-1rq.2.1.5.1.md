# Bead: sase-1rq.2.1.5.1 — Finish the remaining Full CI repairs

[Bead Pages](../README.md) / [sase-1rq.2.1.5](sase-1rq.2.1.5.md) / sase-1rq.2.1.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.5.md) · **Assignee:** `sase-1rq.2.1.5.1.land`
**Created:** 2026-11-07 11:09:41 EST · **Closed:** 2026-11-07 18:37:35 EST
**Plan:** [202611/full\_ci\_remaining\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202611/full_ci_remaining_repairs.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/full_ci_remaining_repairs.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:75c033fca2a65c5156167bcb | attached via sase artifact create --bead |
| related | file:explicit:831a30c22779117a3c26f133 | attached via sase artifact create --bead |
| related | file:explicit:8f73ab815d3b462256446ba3 | attached via sase artifact create --bead |
| related | file:explicit:c4c3bfcaeb49e285a8624f33 | attached via sase artifact create --bead |

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/full_ci_remaining_repairs.md

<!-- sase:links:end -->

## Description

Repair the remaining Files and Main deck races and CI-only snapshot differences, integrate the separately owned bulk golden repair, and prove a first-attempt green Full CI run on master containing every fix.

## Notes

[2026-11-07T23:33:10Z · sase-1rq.2.1.5.1.land] FOLLOW-UP TRIAGE (explicit landing prompt takes precedence over child plan instruction to defer task filing): all ten PROPOSED FOLLOW-UP entries across the four phases reviewed with /sase_new_task, same-type/all-type semantic searches, last-week all-status task sweep, active-epic inventory and plausible j7 scope/child review. No existing active epic was shown to have introduced these unrelated failures; topical overlap alone was not treated as causal ownership.

1. sase-1rq.2.1.5.1.1 note 4, generalized Textual pending-layout remeasure: declined automatic task creation. The actual Files reserve failure and deterministic cache interleave are fixed by da1561407a and pass here. No other failing consumer/reproduction is identified. An upstream report or general helper is an optional extension, not a remaining defect established by this evidence.
2. .2 note 1, archive-reader missing Files reports count=2: new large flake sase-1ry; retained full-check trace reviewed. Root not proven, so size large requests investigation rather than assuming a cache fix.
3. .2 note 2 and .3 note 2, Python 3.14 wait_dependency_resolution._artifact_state import deadlock: corroborate sase-1qb once with both proposing beads and this lander's independent current-tip parallel failure. All 18 focused tests then passed serially without edits.
4. .2 note 3, FINAL/RECORD delivery-hold extension: declined automatic task creation. The watcher is unchanged since before this epic; there is no real FINAL/RECORD delivery reproduction in the note, only an analogy to Main. Main is the approved bounded scope. Do not assert a demonstrated product bug from absent guards alone.
5. .3 note 1, global visual row-overlay cache isolation: declined automatic broadening. The demonstrated leaking stranded-module pair is now isolated before and after each test, and its modal fixture settles real warmup. The other explicitly seeding visual module (agents_waiting) already clears its wait-status cache at its fixture seams. No additional failing pair is identified after this repair. Preserve this suggestion for a concrete order-dependent repro; generalizing the fixture could change unrelated cold/warm golden semantics. The feature task catalog refuses agent creation, and these optional extensions are not refiled as bugs.
6. .4 note 2, archive toast lifetime and incomplete hydration fake: new large flake sase-1rz; independently read first-pass failure, missing .status pump error, and unchanged recapture pass from 23c36bb7de62054ea9523a65d7444ea2.
7. .4 note 3, pager time-band past-True-size1: new large node-specific flake sase-1s0, related to sase-1l5. The suggested duplicate is declined because 1l5 explicitly scopes cause-False-size1 and shared mechanism is unproved. Same retained visual run proves fail/pass for this node.
8. .4 note 4, narrow gate-turns Reply focus: new large flake sase-1s1, related to sase-1r2.6. The strict footer wait exposes the pre-existing unconfirmed focus; it does not change production focus. Full CI attempt 1 succeeded after built-in recapture. Investigate before changing the shared helper.
9. .4 note 5, pager history past-frame-False-size1: corroborate sase-1f9 for the same exact node/capture-stability remediation. Record the observed four-column header offset separately from earlier missing-chrome reports; no shared root claim.

No tests were quarantined and no timeouts, workflow permissions/job lists, recapture limits, comparison tolerance, lint levels or release policy were changed. No follow-up was silently dropped.

[2026-11-07T23:37:35Z · sase-1rq.2.1.5.1.land] Verified all four closed child phases and every note against plan:202611/full_ci_remaining_repairs.md and inherited decisions (test_quarantine=quarantine_flakes, release_merge=gate). Inspected landed commits da1561407a (Files reserve cache remeasurement), 92fc89d83f (bounded Main delivery hold, reader offset and selection sync), 960646e8ce (stranded row repaint/cache isolation and initial stylesheet restyle), dd5567e580 (authorized stale-owner recovery of 109 AGENT PROMPT goldens and hostname/focus fixtures), their regression tests and current production callers. Inspected a before/after representative of the recovered golden family: only the obsolete AGENT PROMPT heading disappears from the empty prompt card. Source matches the reports; no helper re-drive masks Reply and no gate was relaxed.

Integration: audited every non-epic commit from the first fix through current master 291265f08a plus creation-to-first-fix drift. 578a317bcf's compressed stylesheet hydrate preserves rule identity and works with the later parse-free restyle; c732c6e38e's resize-highlight preservation composes with declined-row repaint invalidation. 8668755b35 adds unrelated cache teardown without removing module row-overlay isolation. Contention sharding/leaf import (618dbb5fcf), streamed flag analysis (291265f08a), sidecar connectivity and artifact-backfill changes introduce no duplicate/conflicting epic consumer. origin/master fetched and matches HEAD. No integration code edits were needed.

Independently ran the focused Files/Main regressions, stylesheet snapshot/startup ordering and declined-row patch tests: 18 passed serially at current master. Initial 14-worker run was 17 passed / 1 known import-lock failure in Agents-tab setup before any Main delivery assertion; exact pre-existing _artifact_state deadlock is corroborated on sase-1qb, with retained trace. Child check runs and combined-tree visual evidence reviewed. GitHub API independently confirms Full CI 42414511192, workflow_dispatch, attempt 1, dd5567e5801095c709f7145dd7d6cdfe2a7d8673, success at 2026-11-07T22:55:11Z. All ten executing jobs succeeded, only docs-build and release-core-floor-smoke skipped by design. Ancestry checks prove every fix is contained. Two built-in visual recaptures are explicitly tracked separately from GitHub attempt. Newer scheduled run 42418116452 on the same SHA is still in progress with no failed jobs at final refresh; outer verifier owns latest-tip whole-workflow acceptance. ci_evidence republished. No remaining epic implementation work; no epic-symbol entries.

Follow-up outcomes: .1#4 generalized Textual helper declined (no remaining failing consumer); .2#1 -> sase-1ry; .2#2 and .3#2 -> one corroboration on sase-1qb; .2#3 FINAL/RECORD generalization declined (no reproduced delivery defect); .3#1 global cache fixture generalization declined (known leak fixed, no additional failing pair); .4#2 -> sase-1rz; .4#3 -> sase-1s0 related to sase-1l5 rather than unproven duplicate; .4#4 -> sase-1s1 related to sase-1r2.6; .4#5 -> sase-1f9 corroboration. All new tasks intentionally large because root/seam validation remains. Detailed reasons and evidence are in this epic's FOLLOW-UP TRIAGE note. User-directed task triage completed here rather than passing proposals untriaged to the outer lander.

[2026-11-07T23:39:49Z · sase-1rq.2.1.5.1.land] POST-CLOSE VERIFICATION: just symvision exited 0: All public/private classes/functions are used properly. Both epic/parent-phase symbol scans empty. Linked plan frontmatter changed only status: wip -> done. Normal close also settled parent phase sase-1rq.2.1.5 (delegated work landed); its exact scope/notes were rechecked and an explicit normal close confirmed it already closed. All four new follow-up tasks are ready with retained evidence, both corroborations recorded, and ci_evidence updated with final landing outcomes. No source/golden edits; no just check-full run. Only the plan metadata change is left for host-owned finalization.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.5.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.5.1.land/README.md) | [sase-1rq.2.1.5.1](sase-1rq.2.1.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@82c7e7b`](https://github.com/sase-org/sase--plans/commit/82c7e7b704786152a6e815e3b58651e1346f2823) | chore(plans): mark Full CI repair epic complete | [sase-1rq.2.1.5.1](sase-1rq.2.1.5.1.md) | 2026-11-07 18:40:51 EST |

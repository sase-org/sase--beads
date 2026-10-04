# Bead: sase-1eq.3.1 — Rename sase modules from xprompt to macro

[Bead Pages](../README.md) / [sase-1eq.3](sase-1eq.3.md) / sase-1eq.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.3.md) · **Assignee:** `sase-1eq.3.1.land`
**Created:** 2026-10-02 19:30:23 EDT · **Closed:** 2026-10-03 05:42:54 EDT
**Plan:** [202610/sase\_modules\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_modules_rename.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/sase_modules_rename.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/sase_modules_rename.md

<!-- sase:links:end -->

## Description

Outside the TUI, query-language status macros are shorthands, the xprompt package and sibling modules live on macro paths, identifiers follow a token-aware rename, external plugins still import the old paths through one temporary shim, and a terminology guard holds that boundary.

## Notes

[2026-10-03T09:04:02Z · sase-1eq.3.1.land] LAND AUDIT: Read every child and every note; reviewed commits d9d0cae9f0, 117f5779d3, 5541d4c697, 8de1add72c, the approved plan, and the 25 other commits through master 0676975ef3. Remote origin/master matches. Shorthand wire/digest, legacy readers, guard, MRU filename probe: 39 passed; fresh interpreters verify all 22 shim exports and synthetic module/patch isolation. Proposal batch: 155 passed, only existing sase-172 MRU pruning and sase-1ex publication-binding failures. Readiness: all four phase descendants closed, plan links validate ok, no epic-symbol entries for this epic or parent phase sase-1eq.3. REMAINING EPIC WORK: tests/test_macro_terminology.py added pytest.mark.contract in 8de1add72c but tests/contract_manifest.txt was not regenerated. A fresh tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection fails with exactly that added file missing (other manifest tests pass). This is caused by the epic, not an unrelated slowness proposal. Authoring one small closeout tale: regenerate manifest, verify, then close this epic, mark plan:202610/sase_modules_rename.md done, and close only parent phase sase-1eq.3. Do not close containing epic sase-1eq; no commit/SHA/push/CI wait is part of the closeout.

[2026-10-03T09:05:28Z · sase-1eq.3.1.land] FOLLOW-UP TRIAGE COMPLETE (sase_new_task workflow; searched all statuses, swept last-week tasks, reviewed active epic inventory): .1 note 1 prompt-key legacy MRU assertion is fixed by d8efa2a6e5 and passes now; decline a new task. .1 note 2 busy-cluster parallel flake corroborated existing ready flake sase-1ak (+1 recorded, isolated current pass). .2 note 1 stale three_pane_splits flag is removed by c62e4f1491/d8efa2a6e5; current check feature-flags passed, decline. .3 note 1: pager three-pane tests (25), editor harness, unmount hooks, and split-key tests fixed by d8efa2a6e5; all pass in current 155-pass proposal batch, decline new tasks. The missing plan_publication_payload_batches binding persists even after just install and is caused by 5c7e7514ae (sase-1ex.7); appended DISCOVERED ISSUE to active sase-1ex, which already owns the unused-public facade. The exact MRU pruning failure duplicates ready CI task sase-172 (created nine days before this epic); reproduced batch and fresh isolated serial, +1 recorded. .3 note 2: config token/teardown/isolation and link-follow tests now pass after 0499411408; collection of artifacts_scaffold/deck_card_block_keys/keymaps_app_bindings clean and those tests pass. Decline new load-flake tasks: no specific failing nodes or durable failure evidence were supplied and current reruns are green. Contract-manifest slowness: serial node completed in 55.62s, with no timeout; decline a slowness task. It exposed a distinct epic-caused missing new guard entry, assigned to the landing tale. .3 note 3 intentional old wire/env/plugin/discovery/TUI survivors match deferred parent scopes; guard passes; pr/commit and split_file path leftovers fixed in 5541d4c697. This was a guard heads-up, decline task. .3 note 4: closed sase-1eu whitelist residue removed by 5541d4c697; PaneGrid unused symbols resolved by d8efa2a6e5 (no current PaneGrid lint failures); decline. Publication facade symbols routed to active sase-1ex as above; shim __getattr__ alias resolved. .4 note 1 duplicates that same publication binding proposal; no second task. NEW IN THIS LAND CHECK: memory-history public-symbol lint failures all predate this turn and belong to active sase-1ev; searched tasks and appended a detailed DISCOVERED ISSUE there. No new tasks were created. Resource/catalog/packaging verification: 100 passed; final full lint check 6541adcd5aba30801281d54d4c0423ad stops only on those unrelated memory-history/publication Symvision symbols.

[2026-10-03T09:07:02Z · sase-1eq.3.1.land] LAND TALE REFINEMENT: Current tests/test_contract_manifest.py intentionally pins the entry cap to exact manifest length (73) and documents measured 57.25s serial cost plus curation policy plan:202608/test_suite_tier1.md. Merely regenerating would create 74 entries and fail the cap. The tale must admit the required new guard by that curation policy, retain justified coverage, measure the resulting serial set, and update its exact count/cost comment together. Guard source/import scans currently parse every file even when no xprompt substring exists; a conservative case-insensitive prefilter can reduce the added cost without narrowing the enforced path/NAME/import contract. This remains one bounded medium coding task, not another epic.

[2026-10-03T09:42:54Z · sase-1eq.3.1.land] Landing tale verified: integrated tests/test_macro_terminology.py into tests/contract_manifest.txt by value-per-second curation, keeping cap at 73. Added conservative case-insensitive xprompt substring prefilter before tokenize/AST-parse in both NAME and import scans, retaining path scan, all detection, legacy exceptions, diagnostics. Displaced tests/test_core_eligibility_facade.py (6 tests remain as ordinary tests): change to src/sase/core/eligibility_facade.py still selects it via depth-2 import closure (26 files including it, verified), Rust-side boundary changes escalate via core-identity fingerprint to full suite. Refreshed manifest diff is sorted +macro/-eligibility, net zero. Whole refreshed 73-entry set measured 61.59s serial via .venv/bin/python -m pytest -m contract over manifest paths -p no:randomly --durations=0 (800 passed plus documented sase-1ex publication-binding failure, classified separately; macro 4.47s/3 tests). tests/test_contract_manifest.py updated with count/cost/date/rationale, exact-count assertion kept. Guard+manifest+demoted/finalizer tests: 20 passed. Fixed epic-caused wire straggler from 5541d4c697 in src/sase/agent/launch_executor_types.py as_spawn_kwargs local_xprompts_file->local_macros_file; tests/test_agent_launch_executor.py 8 passed, macro guard 3 passed. just fmt clean. sase tool run check 4b5e08805d8eecdbb5aca789b602b6b1: all lint gates pass except 26 KNOWN symvision (2 publication facade sase-1ex +24 memory-history sase-1ev, witnesses 6541adcd/1af4b029); test-scoped escalated to full suite on manifest change with 5 failures triaged as base, not tale-caused: plugin_latest and publication-binding reproduce on clean base, launch_context and dismissed pass isolated (flakes), agent_launch_executor was KNOWN and is now fixed. No tale-caused failures remain. Follow-up triage already complete per land audit notes 1-3 (sase-172 +1, sase-1ak +1, sase-1ex/sase-1ev DISCOVERED ISSUEs); no new tasks filed. Drift since 0676975ef3 is docs-only. Detailed evidence in land audit notes.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.3.1.land.md) | [sase-1eq.3.1](sase-1eq.3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b4e667d`](https://github.com/sase-org/sase/commit/b4e667d1eb97f8146fafc52a71f73d809508ec3d) | feat(sase-modules): curate macro terminology guard into contract set (sase-1eq.3.1) | [sase-1eq.3.1](sase-1eq.3.1.md) | 2026-10-03 06:11:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.3.1.land--1][1] | Need epic readiness and descendant status for landing | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.3.1.land.md

<!-- sase:referenced-by:end -->

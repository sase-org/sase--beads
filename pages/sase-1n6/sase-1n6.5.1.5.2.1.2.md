# Bead: sase-1n6.5.1.5.2.1.2 — Dispatch and retain the green, probe and exact-SHA source proofs

[Bead Pages](../README.md) / [sase-1n6.5.1.5.2.1](sase-1n6.5.1.5.2.1.md) / sase-1n6.5.1.5.2.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12n.md) · **Assignee:** `sase-1n6.5.1.5.2.1.2` · **Size:** medium
**Created:** 2026-10-20 15:25:39 EDT · **Closed:** 2026-10-23 17:52:11 EDT
**Plan:** [202610/deployed\_qualification\_proof.md](https://github.com/sase-org/sase--plans/blob/main/202610/deployed_qualification_proof.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:00443e8656e3e07fdc958d6c | attached via sase artifact create --bead |
| related | file:explicit:2c9807d13101d7e4f1920d8c | attached via sase artifact create --bead |
| related | file:explicit:380b624f2bd18f6804db1e8e | attached via sase artifact create --bead |
| related | file:explicit:4b085fa3c19a8eccb6d96032 | attached via sase artifact create --bead |
| related | file:explicit:50fd3359e020644fc0d1bc88 | attached via sase artifact create --bead |
| related | file:explicit:5a53615900b27783daf3033f | attached via sase artifact create --bead |
| related | file:explicit:79476a9749f868b5d7c7f2d4 | attached via sase artifact create --bead |
| related | file:explicit:88fe402c602e56f995848006 | attached via sase artifact create --bead |
| related | file:explicit:8bc875efcb830c862a8c0a3d | attached via sase artifact create --bead |
| related | file:explicit:9135aae02237170b0632e49b | attached via sase artifact create --bead |
| related | file:explicit:a76f7706333cb444f33c2532 | attached via sase artifact create --bead |
| related | file:explicit:aa18ca111c87695d17839ee5 | attached via sase artifact create --bead |
| related | file:explicit:d1d05f2daface15a4c425e9f | attached via sase artifact create --bead |
| related | file:explicit:e021a91a561c8a6e9a41f557 | attached via sase artifact create --bead |
| related | file:explicit:ecfaa196c32b298f81e28554 | attached via sase artifact create --bead |
| related | file:explicit:f27fe0e4e8e21041282b6bfd | attached via sase artifact create --bead |
| related | file:explicit:f7620f53009d4743a99d9694 | attached via sase artifact create --bead |
| related | file:explicit:fad2903cc032f8bb9de4f553 | attached via sase artifact create --bead |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

live-proof: once unblock is on remote master, dispatch the green rehearsal, the 0.41.0 probe rehearsal and Full CI at one SHA, monitor them, re-evaluate archived inputs through release_candidate evaluate, register durable evidence and record the acceptance mapping.

## Notes

[2026-10-20T20:54:18Z · sase-1n6.5.1.5.2.1.2] LIVE-PROOF DISPATCH (2026-10-20): unblock commit 3db3b51d53 is on origin/master; compared SHA 4adee846d3c32f0927639193f3d3c2717df946ee contains it. After confirming no queued/running release.yml run, dispatched green rehearse 39495874381 (https://github.com/sase-org/sase/actions/runs/39495874381), 0.41.0 probe rehearse 39495879106 (https://github.com/sase-org/sase/actions/runs/39495879106), and Full CI 39495882967 (https://github.com/sase-org/sase/actions/runs/39495882967). All are workflow_dispatch at the same headSha 4adee846d3c32f0927639193f3d3c2717df946ee. The probe preflight against current source still fails only for missing mobile_pairing_issue (1 of 866). Independent source-containment check: sase-core-revision.txt is 6f354df4d9650777087c06cc937526d95671d493; it is on sase-core origin/master but `git tag --contains` finds no published tag (latest tag v0.42.1). This updates existing DISCOVERED ISSUE #1; the successful qualification of the 0.42.0 wheel cannot prove containment of the pinned source. Await workflow results, retain/re-evaluate artifacts, then keep this phase open and monitor the next daily cut if that gap still prevents trustworthy acceptance.

[2026-10-20T20:55:18Z · sase-1n6.5.1.5.2.1.2] At dispatch time the sase-core v0.42.2 release PR #333 remained OPEN (https://github.com/sase-org/sase-core/pull/333; head eae5bae4ddd057f82f1a0c53c459b2b27cbab2b9), so a next daily cut is pending. After collecting and retaining the three current run results, monitor the bounded next cut if 6f354df4d9650777087c06cc937526d95671d493 is still absent from all published tags; do not close this phase while that gap prevents trustworthy acceptance.

[2026-10-20T21:18:49Z · sase-1n6.5.1.5.2.1.2--1] LIVE-PROOF RESULT — compared SHA 4adee846d3c32f0927639193f3d3c2717df946ee. Run metadata, logs, artifact-download results, and acceptance mapping are retained at file:explicit:79476a9749f868b5d7c7f2d4 and file:explicit:f27fe0e4e8e21041282b6bfd; green-run API metadata is also retained at file:explicit:50fd3359e020644fc0d1bc88.

All three runs were workflow_dispatch, attempt 1, and completed failure at the same SHA: green rehearsal 39495874381 (https://github.com/sase-org/sase/actions/runs/39495874381; created 2026-10-20T20:53:47Z), probe rehearsal 39495879106 (https://github.com/sase-org/sase/actions/runs/39495879106; created 20:53:48Z), Full CI 39495882967 (https://github.com/sase-org/sase/actions/runs/39495882967; created 20:53:50Z).

Both rehearsals failed in identity with SyntaxError: '(' was never closed in the inline Python version reader. Candidate-build was never produced; downstream exercise/qualification downloads reported artifact not found and observation upload had no path. No candidate manifest, green/probe observation, or evaluator input/output exists; neither acceptance result can be re-evaluated. No rerun was eligible or attempted.

REPROOF REQUIRED: repaired the missing closing parenthesis in .github/workflows/release.yml and added a contract assertion compiling the embedded Python command in tests/test_github_actions_release.py. Focused release workflow suite: 26 passed; just fmt completed. The fix needs to land, then green/probe rehearsal and source comparison must be dispatched and retained at one SHA. sase tool run check is being handed to a verify monitor.

PROPOSED FOLLOW-UP: Full CI run 39495882967 failed before lint/tests because build-core setup-uv's cache glob sase-core/**/pyproject.toml matched no files before the core checkout. Lint and test (3.12)/(3.13)/(3.14) were skipped; source proof is unmet. No rerun because the blocking failure was setup, not test-only.

Containment remains a separate blocker. Compared SHA used pin 6f354df4d9650777087c06cc937526d95671d493. Current origin/master eb96eafd442a28cd96ad2e4c35603845d179450c carries pin ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec; that pin is current sase-core master and no published tag contains it. Latest tag is v0.42.1; PR #333 remains OPEN. Do not close this phase; perform the bounded next-daily-cut retry and deployed reproof.

[2026-10-20T22:17:22Z · sase-1n6.5.1.5.2.1.2--2] CHECK RESULT (2026-10-20; ToolRun 2ee1cb3f0eab7d3c90b49c12a8974ffd): `sase tool run check` exited 1 with triage `no_new_failures` (1 KNOWN, 1 FLAKY). Formatting and lint passed; test-scoped escalated to the full suite (`core-identity-changed`) and reported only `test_tui_app_import_stays_under_startup_budget` (KNOWN; tracked by ready task sase-1ic) and `test_behavioral_modules_do_not_dispatch_on_ref_prefix` (FLAKY; tracked by ready task sase-174). Neither failing test file was changed. Evidence snapshot: file:explicit:5a53615900b27783daf3033f; monitor 34j0635h63ge retains the full log. PROPOSED FOLLOW-UP: carry the two existing baseline failures under sase-1ic and sase-174 for their owners; this run found no new failure and no new task is needed. Fresh core-tag check: current pin ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec has no containing published tag; latest is v0.42.1. PR #333 remains OPEN at head 6220ac542bd6dfcfa112ab814137e1be8f16b980. Keep this phase open; bounded ~36-hour next-daily-cut retry will recheck containment, then dispatch aligned green/probe/Full CI only if published-core containment is established.

[2026-10-22T10:26:46Z · sase-1n6.5.1.5.2.1.2--3] NEXT-DAILY-CUT RECHECK (2026-10-22 10:26Z): refreshed sase origin/master is 16d63cf9b0a4fc1a4e5c56a4660d2e45348ea0e8. sase-core-revision.txt remains ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec. The pin is on sase-core origin/master 1503d604844a32a8a93e944addabb0887f8d9bc4, but after fetching tags git tag --contains returns no tag. Latest GitHub-published core release is v0.42.1 (published 2026-10-19T05:15:25Z). sase-core PR #333 remains OPEN at head eb15c8a6187335bce0ec721716cd879b6769cb7b: https://github.com/sase-org/sase-core/pull/333.

The second dispatch prerequisite is also false: sase origin/master still has the malformed inline Python version reader in .github/workflows/release.yml, and its tests/test_github_actions_release.py does not compile that command. The syntax correction and compile assertion are currently only local workspace changes, not landed on origin/master. Per plan, no release or Full CI runs were dispatched and no rerun was attempted. Earlier runs 39495874381, 39495879106 and 39495882967 remain failed at compared SHA 4adee846d3c32f0927639193f3d3c2717df946ee without the required candidate, probe or source proof; retained evidence remains file:explicit:79476a9749f868b5d7c7f2d4 and acceptance mapping file:explicit:f27fe0e4e8e21041282b6bfd. Keep this assigned phase open until the pin is contained by a published tag and the repair plus contract test land, then perform deployed reproof.

[2026-10-23T18:10:27Z · sase-1n6.5.1.5.2.1.2] LIVE-PROOF REDISPATCH (2026-10-23): all earlier repair prerequisites now landed on origin/master. Verified unblock 3db3b51d53, identity version-reader repair/compile assertion ba7ab4e96b, build-core cache ordering repair b2a4c380cf, and exact published pin move b97e6c4b91. Compared SHA is bdec291c77b0de1aab4c00abecef7430761db736, also containing the pytest -p selector repair. Source pin 246e28743538b6cd4d4e098b6960085c3e8ef5a9 is contained by published v0.42.2 (published 2026-10-23T16:29:37Z). No tracked source edits in this turn; the remaining work is bounded live proof and evidence retention, so no additional child implementation epic was necessary.

After confirming no queued/running release.yml runs, dispatched green rehearsal 40000653149 (https://github.com/sase-org/sase/actions/runs/40000653149), probe rehearsal 40000657197 (https://github.com/sase-org/sase/actions/runs/40000657197), and Full CI 40000661173 (https://github.com/sase-org/sase/actions/runs/40000661173). Verified workflow_dispatch, attempt 1, created 18:06:59Z / 18:07:01Z / 18:07:02Z, all headSha equal to compared SHA. No reruns attempted. Full CI cron remains 17 */2 * * *; next nominal 18:17Z. Release concurrency has green running and probe pending; do not dispatch another release while pending.

Intended/sealed core is now 0.42.2. Following live-proof step 2's changed-pin rule, selected nearest older complete core 0.42.1 (all five PyPI suffixes verified). Green preflight exposes all 875 bindings; probe lacks nine: classify_publication_error, classify_replay_paths, decide_publication_failure_accounting, decide_replay_apply, decide_replay_byte_divergence, decide_replay_hood_merge, repair_session_manifest_entry, select_publication_drain, sudo_fit_ledger. The historical 0.41.0 also lacks mobile_pairing_issue; 0.42.1 contains it. The updated probe acceptance must name its actual missing bindings, as required by the original ancestor contract, while preserving intended 0.42.2 and tested 0.42.1. Inventory digest is a4ff4aa99b83777d444dcc526bc392f0f8249be21086443de821d76ac43d1165.

Durable readiness/preflight record: file:explicit:4b085fa3c19a8eccb6d96032. Aligned dispatch receipts: file:explicit:f7620f53009d4743a99d9694. Monitor will bound polling below four hours and carry steps 5-10: retain artifacts/jobs/counts/advisories, re-evaluate archived green/probe inputs, prove exact-SHA source blocking jobs, honor rerun_once=once only when eligible, retain acceptance mapping, and close only this phase after epic-symbols is clean. Dispatch is not acceptance. Outer DISCOVERED ISSUE #1 remains open: tag containment is independently true for this pair, but manifest/evaluator enforcement remains absent.

[2026-10-23T21:38:34Z · sase-1n6.5.1.5.2.1.2--1] PROPOSED FOLLOW-UP: Existing modal-resize timeout still blocks live qualification — at clean compared SHA bdec291c77b0de1aab4c00abecef7430761db736, green run 40000653149 test 3.13/3.14 and source run 40000661173 all three test legs fail tests/ace/tui/test_custom_gate_modal_sizing.py::test_compact_scroll_refits_after_resize after 5 seconds. Earlier independent report is on sase-1nn.6, pointing to sase-1nn.4. Source 3

… and 9598 more characters

## Dependencies

- **Depends on:** [sase-1n6.5.1.5.2.1.1](sase-1n6.5.1.5.2.1.1.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.5.1.5.2.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.1.5.2.1.2.md) | [sase-1n6.5.1.5.2.1.2](sase-1n6.5.1.5.2.1.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ba7ab4e`](https://github.com/sase-org/sase/commit/ba7ab4e96bce13fdf71b9e429bffe92a8cf39205) | fix(release): repair identity version validation | [sase-1n6.5.1.5.2.1.2](sase-1n6.5.1.5.2.1.2.md) | 2026-10-22 06:28:03 EDT |
| sase | [`2d1e7fd`](https://github.com/sase-org/sase/commit/2d1e7fd48646c6240f99ba6ac44f5c6e0f75f3c0) | fix(release): retain qualification observations after evaluation | [sase-1n6.5.1.5.2.1.2](sase-1n6.5.1.5.2.1.2.md) | 2026-10-23 17:53:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:13d][1] | Research which agents stalled the sase-1n6 epic: unblock epic and its phases | 1 |
| read-by | [agent:sase-1n6.5.1.5.2.1.2--3][2] | Need the current phase scope, prior notes, and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.13d/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.1.5.2.1.2.md

<!-- sase:referenced-by:end -->

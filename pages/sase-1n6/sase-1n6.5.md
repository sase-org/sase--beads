# Bead: sase-1n6.5 — Qualify the candidate against the published core

[Bead Pages](../README.md) / [sase-1n6](README.md) / sase-1n6.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11y](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11y.md) · **Assignee:** `sase-1n6.5` · **Size:** large
**Created:** 2026-10-19 16:40:08 EDT
**Plan:** [202610/e2\_release\_train\_steward.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_release_train_steward.md)

## Description

qualify: ci.yml gains ref and core-source inputs, a versioned N1 inventory decides what blocks, and release.yml qualifies against the exact published core with fail-closed evidence.

## Notes

[2026-10-20T04:07:35Z · sase-1n6.5.1.4] PUBLISH INTEGRATION SEAM from release-wiring (sase-1n6.5.1.4): publication (sase-1n6.6) must depend on the qualify job verdict plus exercise, never on the qualify-ci aggregate. qualify exposes verdict/observation/token/run-id/attempt/candidate-id/generation/intended-core-version/tested-core-version outputs; its result is success-with-red-verdict only via the always() final verdict step, so publish needs an explicit status condition such as needs.qualify.outputs.verdict == pass. That condition must pass through required verdicts even when an advisory ancestor failed: default success propagation would silently skip publication after a red advisory job fails qualify-ci. Red qualification observations persist on the draft (release) or as artifacts (rehearse) under candidate-gen<N>-qualification-run<R>-attempt<A>.json.

[2026-10-20T05:35:34Z · sase-1n6.5.1.5.2] Qualification live proofs still outstanding. sase-1n6.5.1.5.2 could not dispatch release.yml rehearse at 400572eab6: reusable ci.yml rejected job-level ${{ runner.temp }} (HTTP 422). A step-level fix is landing with that phase. Pre-existing toobig in tests/test_release_watch_health.py (1253 lines) still fails just lint, so qualify-ci lint will stay red until toobig_split. Publish seam from sase-1n6.5.1.4 is unchanged.

[2026-10-20T21:18:49Z · sase-1n6.5.1.5.2.1.2--1] LIVE-PROOF RESULT — compared SHA 4adee846d3c32f0927639193f3d3c2717df946ee. Run metadata, logs, artifact-download results, and acceptance mapping are retained at file:explicit:79476a9749f868b5d7c7f2d4 and file:explicit:f27fe0e4e8e21041282b6bfd; green-run API metadata is also retained at file:explicit:50fd3359e020644fc0d1bc88.

All three runs were workflow_dispatch, attempt 1, and completed failure at the same SHA: green rehearsal 39495874381 (https://github.com/sase-org/sase/actions/runs/39495874381; created 2026-10-20T20:53:47Z), probe rehearsal 39495879106 (https://github.com/sase-org/sase/actions/runs/39495879106; created 20:53:48Z), Full CI 39495882967 (https://github.com/sase-org/sase/actions/runs/39495882967; created 20:53:50Z).

Both rehearsals failed in identity with SyntaxError: '(' was never closed in the inline Python version reader. Candidate-build was never produced; downstream exercise/qualification downloads reported artifact not found and observation upload had no path. No candidate manifest, green/probe observation, or evaluator input/output exists; neither acceptance result can be re-evaluated. No rerun was eligible or attempted.

REPROOF REQUIRED: repaired the missing closing parenthesis in .github/workflows/release.yml and added a contract assertion compiling the embedded Python command in tests/test_github_actions_release.py. Focused release workflow suite: 26 passed; just fmt completed. The fix needs to land, then green/probe rehearsal and source comparison must be dispatched and retained at one SHA. sase tool run check is being handed to a verify monitor.

PROPOSED FOLLOW-UP: Full CI run 39495882967 failed before lint/tests because build-core setup-uv's cache glob sase-core/**/pyproject.toml matched no files before the core checkout. Lint and test (3.12)/(3.13)/(3.14) were skipped; source proof is unmet. No rerun because the blocking failure was setup, not test-only.

Containment remains a separate blocker. Compared SHA used pin 6f354df4d9650777087c06cc937526d95671d493. Current origin/master eb96eafd442a28cd96ad2e4c35603845d179450c carries pin ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec; that pin is current sase-core master and no published tag contains it. Latest tag is v0.42.1; PR #333 remains OPEN. Do not close this phase; perform the bounded next-daily-cut retry and deployed reproof.

[2026-10-20T22:18:01Z · sase-1n6.5.1.5.2.1.2--2] QUALIFY PHASE HANDOFF (2026-10-20): ToolRun 2ee1cb3f0eab7d3c90b49c12a8974ffd exited 1 with no_new_failures; only existing KNOWN/FLAKY tests failed (sase-1ic and sase-174), while format/lint passed. Snapshot: file:explicit:5a53615900b27783daf3033f. Aligned deployed attempts at SHA 4adee846d3c32f0927639193f3d3c2717df946ee failed before required evidence: green/probe identity errors, Full CI setup failure. Current pin ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec is not contained by a published tag (latest v0.42.1); PR #333 remains OPEN at head 6220ac542bd6dfcfa112ab814137e1be8f16b980. Keep qualification acceptance open pending bounded retry.

[2026-10-22T10:27:01Z · sase-1n6.5.1.5.2.1.2--3] QUALIFICATION HANDOFF (2026-10-22): the deployed-proof retry rechecked sase origin/master 16d63cf9b0a4fc1a4e5c56a4660d2e45348ea0e8 and the current core pin ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec. The pin is an ancestor of core origin/master 1503d604844a32a8a93e944addabb0887f8d9bc4 but is contained by no fetched tag; latest published core release is v0.42.1, and PR #333 remains OPEN at eb15c8a6187335bce0ec721716cd879b6769cb7b. The release identity syntax repair and command-compilation contract test are still absent from sase origin/master (only local workspace changes), so no proof workflows were dispatched. The deployed-proof phase remains open; previous runs 39495874381, 39495879106 and 39495882967 at SHA 4adee846d3c32f0927639193f3d3c2717df946ee did not produce acceptable qualification/source proof. Evidence bundle file:explicit:79476a9749f868b5d7c7f2d4; mapping file:explicit:f27fe0e4e8e21041282b6bfd.

[2026-10-23T21:42:43Z · sase-1n6.5.1.5.2.1.2--1] REPROOF REQUIRED (2026-10-23): compared SHA bdec291c77b0de1aab4c00abecef7430761db736. Green https://github.com/sase-org/sase/actions/runs/40000653149, probe https://github.com/sase-org/sase/actions/runs/40000657197, and source Full CI https://github.com/sase-org/sase/actions/runs/40000661173 all completed failure at attempt 1. No reruns or further dispatches performed.

Acceptance mapping: file:explicit:88fe402c602e56f995848006. Full raw bundle (133 files, original candidate ZIPs, per-job evidence, complete paginated job/artifact responses, logs, local replays and digest verification): file:explicit:d1d05f2daface15a4c425e9f. Required-job/source/advisory summary: file:explicit:2c9807d13101d7e4f1920d8c. Individual deployed manifests: green file:explicit:8bc875efcb830c862a8c0a3d, probe file:explicit:9135aae02237170b0632e49b.

Both qualify jobs lost their observation upload because release.yml's inline asset reader was missing a closing parenthesis and hid stderr. Fixed asset/reason reads to pass filenames through sys.argv and retain diagnostics. Existing green/probe transport tests now execute the actual full workflow evaluate step and validate the upload outputs; both reproduced the old error, and all 32 focused release/transport tests pass with the repair. Required check is running under ToolRun 63ce16272c90ed2e5dca334ffbf86a98; its final verification note must precede closure. Actionlint reports identical pre-existing SC2012 findings on clean base and changed workflow; workflow-only validation passes.

LIVE ACCEPTANCE UNMET: green lint and test 3.12 passed; test 3.13/3.14 failed the modal-resize timeout. Probe lint names all nine missing bindings with installed 0.42.1 versus sealed/intended 0.42.2, but neither workflow retained an observation artifact. Local reconstructed QUALIFY_RED reports are diagnostic only: green has test-only rerun eligibility, probe is not eligible. Archived empty observation lists correctly refuse qualification/exercise and are not rerun-eligible. Source lint passes all 875 bindings from pin 246e28743538b6cd4d4e098b6960085c3e8ef5a9, but all three source test legs are red (3.12 also deck Ctrl-J timeout). Source is separately eligible for at most one test retry; none was consumed because this transport repair needs new aligned runs. Wheel exercise legs on both OSes also fail UPGRADE_NO_INSTALLABLE_PREVIOUS; sdist legs pass. Visual-test is advisory red; other advisories pass. Phase PROPOSED FOLLOW-UP notes retain existing owners and unresolved exercise diagnostics.

After the repair lands and unrelated blocking tests are addressed: fetch master, verify repair ancestry and current core completeness/containment, choose the nearest older incompatible probe if the pin changed, and ensure no release run is pending. Dispatch back-to-back `gh workflow run release.yml -R sase-org/sase --ref master -f mode=rehearse`, the same plus `-f probe_core_version=0.42.1` (only if intended remains 0.42.2), and `gh workflow run full.yml -R sase-org/sase --ref master`. Verify equal headSha, monitor under four hours, retain actual workflow observations and re-evaluate with the shared evaluator. No third release while probe is pending. Honor once-only test reruns, never retry missing/setup/lint failures. This phase uses the plan step-8 repair handoff after local verification; no ancestor is closed and none may claim acceptance from these red runs.

Outer DISCOVERED ISSUE #1 on sase-1n6 REMAINS OPEN. Published v0.42.2 independently contains the pin, but manifest/evaluator do not enforce containment; archived core_source_pin is still the requirement string sase-core-rs==0.42.2. Qualification does not fix that separate issue.

[2026-10-23T21:52:05Z · sase-1n6.5.1.5.2.1.2--1] FINAL LOCAL VERIFICATION for the REPROOF REQUIRED repair: evidence file:explicit:e021a91a561c8a6e9a41f557 supplements the pending-check paragraph in mapping file:explicit:88fe402c602e56f995848006. The observation-reader repair passes all 32 focused release/transport tests, including two tests that reproduce the old deployed error before the fix. Formatting and diff checks pass. Required check 63ce16272c90ed2e5dca334ffbf86a98 completed exit 1: all lint stages passed; test lane 57,203 passed / 5 failed / 17 skipped. Stored triage is four KNOWN TUI failures plus one NEW artifact-tab descriptor assertion. That one passes on the unchanged repaired tree and on clean HEAD, with all 13 tests in its file passing on clean HEAD; the suite-context follow-up is recorded on the assigned phase. Original nonzero exit and NEW

… and 512 more characters

## Dependencies

- **Depends on:** [sase-1n6.2](sase-1n6.2.md) ✓ · ⧖ 2026-10-19
- **Depends on:** [sase-1n6.3](sase-1n6.3.md) ✓ · ⧖ 2026-10-19
- **Depends on:** [sase-1n6.4](sase-1n6.4.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.6](sase-1n6.6.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.md) | [sase-1n6.5](sase-1n6.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:13d][1] | Research which agents stalled the sase-1n6 epic: in-progress phases | 1 |
| read-by | [agent:research.2a.cld][2] | E3 readiness: E2 status | 1 |
| read-by | [agent:research.2a.grk][3] | Need remaining open E2 phase statuses and blockers before designing E3 | 1 |
| read-by | [agent:research.2a.mus][4] | E3 readiness: remaining E2 phases status | 1 |
| read-by | [agent:sase-1n6.5.1.1][5] | Need parent-phase notes and inherited qualification decisions | 1 |
| read-by | [agent:sase-1n6.5.1.4][6] | Need epic DECISIONS and land context | 1 |
| read-by | [agent:sase-1n6.5.1.5.2][7] | Need outer release-train phase live-acceptance requirements | 1 |
| read-by | [agent:sase-1n6.5.1.5.2.1.2--3][8] | Record current published-core containment blocker on the outer qualification phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.13d/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.cld/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.grk/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.mus/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.1/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.4/README.md
[7]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.5.2/README.md
[8]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.1.5.2.1.2.md

<!-- sase:referenced-by:end -->

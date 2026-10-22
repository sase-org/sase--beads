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
| read-by | [agent:sase-1n6.5.1.1][1] | Need parent-phase notes and inherited qualification decisions | 1 |
| read-by | [agent:sase-1n6.5.1.4][2] | Need epic DECISIONS and land context | 1 |
| read-by | [agent:sase-1n6.5.1.5.2][3] | Need outer release-train phase live-acceptance requirements | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.4/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.5.2/README.md

<!-- sase:referenced-by:end -->

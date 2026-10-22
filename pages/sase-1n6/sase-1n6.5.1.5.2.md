# Bead: sase-1n6.5.1.5.2 — Retain green and wrong-core rehearsal proofs

[Bead Pages](../README.md) / [sase-1n6.5.1.5](sase-1n6.5.1.5.md) / sase-1n6.5.1.5.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1n6.5.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.1.land.md) · **Assignee:** `sase-1n6.5.1.5.2` · **Size:** medium
**Created:** 2026-10-20 00:28:15 EDT
**Plan:** [202610/qualification\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/qualification_landing_repairs.md)

## Description

deployed-proof: exercise the host-landed repair through release rehearsals and retain the exact-SHA source-CI comparison and candidate observations.

## Notes

[2026-10-20T05:35:05Z · sase-1n6.5.1.5.2] DEPLOYED-PROOF STATUS at repair SHA 400572eab602681aa64f44653484a1dfc9ab0b38 (origin/master at start). Live rehearsals could not start: `gh workflow run release.yml -R sase-org/sase --ref master -f mode=rehearse` at 2026-10-20T05:12:52Z returned HTTP 422 because reusable ci.yml job `test` set job-level env `SASE_QUALIFY_EVIDENCE_PATH: ${{ runner.temp }}/qualify-session.json`. GitHub rejects the `runner` context there at parse time (`Line: 374, Col: 35: Unrecognized named-value: 'runner'`), so release.yml cannot call ci.yml. That is why Full CI / ci.yml runs at this SHA complete in 0s with "workflow file issue". The job-level env dates to 8afb1b7e57 (ci-evidence); this phase moved it onto the two test run steps, where `runner` is valid. Contract test `test_test_commands_and_plugin_activation_stay_reporting_only` now asserts the step-level path and that job `test` has no env map.

Also split the three QUALIFY_RED tests the repair added to tests/test_release_candidate.py (1034 lines, over toobig 1000) into tests/test_release_candidate_qualify_red.py; original file is 826 lines. Contract manifest recuration 83→84 redistributes those same tests. sase tool run check 4421a924749bdf13b133ddb7ea6bf706 succeeded (lint gates except toobig + scoped tests). epic-symbols clean.

REMAINING (do not close this phase until both live proofs and exact-SHA source comparison exist): after this runner-context fix is on remote master, dispatch `gh workflow run release.yml -R sase-org/sase --ref master -f mode=rehearse`, identify the run by dispatch time and headSha, retain URL/observation/manifest, re-evaluate through `release_candidate evaluate`. Probe core: published complete 0.34.48 (PyPI wheel+sdist; lacks pyo3 `bead_set_link_projections`, first tagged v0.34.53). Source pin dd817d5679409aaa2eefa0c3e517e8cfe91c37ef is sase-core origin/master and is contained in no published tag; sase-org/sase-core PR #333 (v0.42.2) is the in-flight daily cut. Do not credit a green qualification as satisfying that outer containment gap (already DISCOVERED ISSUE on sase-1n6). Observation asset: candidate-gen{generation}-qualification-run{RUN}-attempt{N}.json; rehearse artifact qualification-observation-run-{run}-attempt-{attempt}.

[2026-10-20T05:35:24Z · sase-1n6.5.1.5.2] PROPOSED FOLLOW-UP: tests/test_release_watch_health.py is 1253 lines and fails just lint toobig — reproduces identically at 54a9c14d23 (Master Gate lint job 118449395477, sole violation) and is owned by the toobig_split routine, not qualification. qualify-ci runs just lint, so a green rehearsal at current master cannot pass until that file is split. Do not treat a QUALIFY_RED caused only by this pre-existing toobig as a qualification-transport defect.

[2026-10-20T21:18:49Z · sase-1n6.5.1.5.2.1.2--1] LIVE-PROOF RESULT — compared SHA 4adee846d3c32f0927639193f3d3c2717df946ee. Run metadata, logs, artifact-download results, and acceptance mapping are retained at file:explicit:79476a9749f868b5d7c7f2d4 and file:explicit:f27fe0e4e8e21041282b6bfd; green-run API metadata is also retained at file:explicit:50fd3359e020644fc0d1bc88.

All three runs were workflow_dispatch, attempt 1, and completed failure at the same SHA: green rehearsal 39495874381 (https://github.com/sase-org/sase/actions/runs/39495874381; created 2026-10-20T20:53:47Z), probe rehearsal 39495879106 (https://github.com/sase-org/sase/actions/runs/39495879106; created 20:53:48Z), Full CI 39495882967 (https://github.com/sase-org/sase/actions/runs/39495882967; created 20:53:50Z).

Both rehearsals failed in identity with SyntaxError: '(' was never closed in the inline Python version reader. Candidate-build was never produced; downstream exercise/qualification downloads reported artifact not found and observation upload had no path. No candidate manifest, green/probe observation, or evaluator input/output exists; neither acceptance result can be re-evaluated. No rerun was eligible or attempted.

REPROOF REQUIRED: repaired the missing closing parenthesis in .github/workflows/release.yml and added a contract assertion compiling the embedded Python command in tests/test_github_actions_release.py. Focused release workflow suite: 26 passed; just fmt completed. The fix needs to land, then green/probe rehearsal and source comparison must be dispatched and retained at one SHA. sase tool run check is being handed to a verify monitor.

PROPOSED FOLLOW-UP: Full CI run 39495882967 failed before lint/tests because build-core setup-uv's cache glob sase-core/**/pyproject.toml matched no files before the core checkout. Lint and test (3.12)/(3.13)/(3.14) were skipped; source proof is unmet. No rerun because the blocking failure was setup, not test-only.

Containment remains a separate blocker. Compared SHA used pin 6f354df4d9650777087c06cc937526d95671d493. Current origin/master eb96eafd442a28cd96ad2e4c35603845d179450c carries pin ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec; that pin is current sase-core master and no published tag contains it. Latest tag is v0.42.1; PR #333 remains OPEN. Do not close this phase; perform the bounded next-daily-cut retry and deployed reproof.

[2026-10-20T22:17:50Z · sase-1n6.5.1.5.2.1.2--2] LIVE-PROOF HANDOFF UPDATE (2026-10-20): ToolRun 2ee1cb3f0eab7d3c90b49c12a8974ffd (`sase tool run check`) exited 1 with triage no_new_failures: formatting/lint passed; only existing KNOWN import-budget (sase-1ic) and FLAKY ref-prefix (sase-174) tests failed. Evidence snapshot file:explicit:5a53615900b27783daf3033f; monitor 34j0635h63ge retains full output. The deployed runs remain red at aligned SHA 4adee846d3c32f0927639193f3d3c2717df946ee: green 39495874381 and probe 39495879106 failed before candidate/observation output; Full CI 39495882967 failed before lint/tests. Current pin ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec is still in no published tag (latest v0.42.1); PR #333 remains OPEN at head 6220ac542bd6dfcfa112ab814137e1be8f16b980. Keep deployed-proof open and retry after the bounded ~36-hour daily-cut wait.

[2026-10-22T10:26:51Z · sase-1n6.5.1.5.2.1.2--3] NEXT-DAILY-CUT HANDOFF (2026-10-22): refreshed sase origin/master is 16d63cf9b0a4fc1a4e5c56a4660d2e45348ea0e8. The current sase-core-revision pin ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec is on core origin/master 1503d604844a32a8a93e944addabb0887f8d9bc4 but has no containing tag after tag fetch; latest published release is v0.42.1. PR #333 is OPEN at head eb15c8a6187335bce0ec721716cd879b6769cb7b (https://github.com/sase-org/sase-core/pull/333). Also, origin/master still has the malformed release identity Python command and lacks the contract assertion that compiles it; the correction/assertion exist only as local workspace changes. Both prerequisites for dispatch are false, so the child phase dispatched nothing and remains open. Earlier aligned runs 39495874381, 39495879106 and 39495882967 at SHA 4adee846d3c32f0927639193f3d3c2717df946ee remain failed and do not supply candidate, probe or exact-SHA source proof; retained bundle file:explicit:79476a9749f868b5d7c7f2d4 and mapping file:explicit:f27fe0e4e8e21041282b6bfd.

## Dependencies

- **Depends on:** [sase-1n6.5.1.5.1](sase-1n6.5.1.5.1.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.5.1.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.5.2/README.md) | [sase-1n6.5.1.5.2](sase-1n6.5.1.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e10fa95`](https://github.com/sase-org/sase/commit/e10fa95c0dec856fe1cc0426bfb35fac1f0834a8) | fix(ci): move qualify session path off reusable job env | [sase-1n6.5.1.5.2](sase-1n6.5.1.5.2.md) | 2026-10-20 01:36:57 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n6.5.1.5.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.5.2/README.md

<!-- sase:referenced-by:end -->

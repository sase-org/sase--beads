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

# Bead: sase-1n6.5.1 — Qualify release candidates against their exact published core

[Bead Pages](../README.md) / [sase-1n6.5](sase-1n6.5.md) / sase-1n6.5.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1n6.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.md) · **Assignee:** `sase-1n6.5.1.land`
**Created:** 2026-10-19 20:21:18 EDT
**Plan:** [202610/published\_core\_qualification.md](https://github.com/sase-org/sase--plans/blob/main/202610/published_core_qualification.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/published_core_qualification.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/published_core_qualification.md

<!-- sase:links:end -->

## Description

Complete sase-1n6.5 with candidate-bound qualification evidence, published-core CI, and green and deliberately red rehearsal proofs.

## Notes

[2026-10-20T04:24:20Z · sase-1n6.5.1.land] LANDING REVIEW at 54a9c14d2393ed168504eb64b2335b2e8fd1825e: read this epic, every child (.1-.4), every child note, the approved child and parent plans, and the four epic commits 443fba33d9 / 9edbacd4ef / 8afb1b7e57 / 54a9c14d23. Child PROPOSED FOLLOW-UP entries: none. Inherited DECISIONS remain workflow steward, daily cadence, and memory changes reserved for the outer exit phase; no memory changes needed here. Reviewed intervening 5003ef69bd (core pin / steward adapter), de1d960d11 (deck presentation), 23cccbc969 (release fact reader), 112a5f4757 (health composition). The steward delegates to release_candidate evaluate, so preserve that shared contract and its candidate-gen observation asset-name filter. Remote master matches reviewed HEAD. No epic-symbol entries remain.

Remaining epic defects, reproduced from actual code: (1) ci.yml writer steps export no GITHUB_TOKEN and resolve_job_id matches unqualified lint/test names against prefixed reusable-call API names; both no-token and mocked qualify-ci / lint return None, making all evidence fail numeric identity. (2) release.yml uses nonexistent actions/runs/R/attempts/N/artifacts (live GET on run 39360520824 returned 404 while run-scoped artifacts returned 200); --paginate output is multiple JSON documents, but the zip downloader and collector accept one JSON document/list, so multi-page input raises Extra data. (3) draft attachment checks for candidate-genN-qualification-runR-attemptA.json but uploads qualification-observation.json, so the steward misses it and later attempts collide. (4) probe lint records installed version only from .venv, although failed preflight prevents setup; evaluator returns on binding mismatch before preserving missing_bindings in failure diagnostics (reproduced with required_binding). (5) a fetch-error red observation stores null workflow_run_id/current_attempt despite supplied expected run/attempt; re-evaluation rejects it as provenance disagreement instead of preserving typed QUALIFY_RED. Docs also overstate rerun eligibility as any failed blocker. These remain epic work, with executable workflow/producer-to-consumer regressions required; local phase contract passes did not exercise these seams. Live green/probe proofs are not yet present; listed release runs are older SHAs.

FOLLOW-UP TRIAGE: no child proposals to create, corroborate, or decline. A separately discovered pre-existing manifest core-source-pin/containment gap was processed through /sase_new_task; no duplicate task found, and a DISCOVERED ISSUE was attached to causal active outer epic sase-1n6 (exact-build/core-pin scope). No new task created. It is not silently counted as satisfied by a green qualification. A remaining-work child epic will serialize one bounded repair phase and a live-proof phase, because the approved acceptance requires exercising deployed workflow bytes after the repair is host-landed; a tale cannot wait on its own eventual commit. Keep this epic and phase sase-1n6.5 open until those proofs exist.

[2026-10-20T05:35:29Z · sase-1n6.5.1.5.2] sase-1n6.5.1.5.2 deployed-proof blocked before rehearsal: release.yml dispatch at 400572eab6 422'd because ci.yml test job-level env used ${{ runner.temp }} (parse error on reusable call). Fix is in this phase's pending commit (step-level SASE_QUALIFY_EVIDENCE_PATH). Live green/probe proofs and exact-SHA source comparison are still required after that SHA is on master. Probe candidate: sase-core-rs 0.34.48. Source pin dd817d56 is in no published tag; do not credit qualification for the sase-1n6 containment gap.

[2026-10-20T21:18:49Z · sase-1n6.5.1.5.2.1.2--1] LIVE-PROOF RESULT — compared SHA 4adee846d3c32f0927639193f3d3c2717df946ee. Run metadata, logs, artifact-download results, and acceptance mapping are retained at file:explicit:79476a9749f868b5d7c7f2d4 and file:explicit:f27fe0e4e8e21041282b6bfd; green-run API metadata is also retained at file:explicit:50fd3359e020644fc0d1bc88.

All three runs were workflow_dispatch, attempt 1, and completed failure at the same SHA: green rehearsal 39495874381 (https://github.com/sase-org/sase/actions/runs/39495874381; created 2026-10-20T20:53:47Z), probe rehearsal 39495879106 (https://github.com/sase-org/sase/actions/runs/39495879106; created 20:53:48Z), Full CI 39495882967 (https://github.com/sase-org/sase/actions/runs/39495882967; created 20:53:50Z).

Both rehearsals failed in identity with SyntaxError: '(' was never closed in the inline Python version reader. Candidate-build was never produced; downstream exercise/qualification downloads reported artifact not found and observation upload had no path. No candidate manifest, green/probe observation, or evaluator input/output exists; neither acceptance result can be re-evaluated. No rerun was eligible or attempted.

REPROOF REQUIRED: repaired the missing closing parenthesis in .github/workflows/release.yml and added a contract assertion compiling the embedded Python command in tests/test_github_actions_release.py. Focused release workflow suite: 26 passed; just fmt completed. The fix needs to land, then green/probe rehearsal and source comparison must be dispatched and retained at one SHA. sase tool run check is being handed to a verify monitor.

PROPOSED FOLLOW-UP: Full CI run 39495882967 failed before lint/tests because build-core setup-uv's cache glob sase-core/**/pyproject.toml matched no files before the core checkout. Lint and test (3.12)/(3.13)/(3.14) were skipped; source proof is unmet. No rerun because the blocking failure was setup, not test-only.

Containment remains a separate blocker. Compared SHA used pin 6f354df4d9650777087c06cc937526d95671d493. Current origin/master eb96eafd442a28cd96ad2e4c35603845d179450c carries pin ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec; that pin is current sase-core master and no published tag contains it. Latest tag is v0.42.1; PR #333 remains OPEN. Do not close this phase; perform the bounded next-daily-cut retry and deployed reproof.

[2026-10-20T22:17:56Z · sase-1n6.5.1.5.2.1.2--2] QUALIFICATION LIVE-PROOF STATUS (2026-10-20): check ToolRun 2ee1cb3f0eab7d3c90b49c12a8974ffd exited 1, triaged no_new_failures with only established KNOWN/FLAKY tests (trackers sase-1ic and sase-174); format/lint passed. Evidence: file:explicit:5a53615900b27783daf3033f. Aligned green/probe/Full CI runs at SHA 4adee846d3c32f0927639193f3d3c2717df946ee did not produce required proof: rehearsals failed in identity before artifacts; Full CI failed before lint/test. Current pin ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec remains absent from published tags after fetching tags; latest v0.42.1; core PR #333 OPEN at 6220ac542bd6dfcfa112ab814137e1be8f16b980. Child phase stays open for bounded daily-cut retry.

[2026-10-22T10:26:56Z · sase-1n6.5.1.5.2.1.2--3] LIVE-PROOF RETRY STATUS (2026-10-22): after the bounded 36-hour wait, refreshed sase origin/master is 16d63cf9b0a4fc1a4e5c56a4660d2e45348ea0e8. Current core source pin ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec is on core origin/master 1503d604844a32a8a93e944addabb0887f8d9bc4, but no fetched tag contains it; latest published core release is v0.42.1. PR #333 remains OPEN at head eb15c8a6187335bce0ec721716cd879b6769cb7b. The release identity syntax fix and compiling contract assertion still have not landed on sase origin/master, so both dispatch gates remain false. No workflows were dispatched; keep child live-proof phase open. Prior aligned runs 39495874381, 39495879106 and 39495882967 remain failed at SHA 4adee846d3c32f0927639193f3d3c2717df946ee without acceptable qualification artifacts; see file:explicit:79476a9749f868b5d7c7f2d4 and acceptance mapping file:explicit:f27fe0e4e8e21041282b6bfd.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.5.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.1.land.md) | [sase-1n6.5.1](sase-1n6.5.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n6.5.1.1][1] | Need the child epic decisions for the evidence phase | 1 |
| read-by | [agent:sase-1n6.5.1.3][2] | Need parent epic DECISIONS and remaining phases | 1 |
| read-by | [agent:sase-1n6.5.1.4][3] | Need epic DECISIONS and land context | 1 |
| read-by | [agent:sase-1n6.5.1.5.2][4] | Need original qualification landing notes and remaining live proofs | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.4/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.5.2/README.md

<!-- sase:referenced-by:end -->

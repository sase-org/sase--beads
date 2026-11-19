# Bead: sase-1tc.5.1.2 — Project candidate fields in Rust and prove the full CLI path

[Bead Pages](../README.md) / [sase-1tc.5.1](sase-1tc.5.1.md) / sase-1tc.5.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tc.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.5.md) · **Assignee:** `sase-1tc.5.1.2` · **Size:** medium
**Created:** 2026-11-19 09:15:29 EST · **Closed:** 2026-11-19 14:42:52 EST
**Plan:** [202611/triage\_owner\_settlement.md](https://github.com/sase-org/sase--plans/blob/main/202611/triage_owner_settlement.md)

## Description

candidate_projection: replace full Python task hydration with a narrow Rust candidate query, retain existing budgets and diagnostics, and prove exact node and file owners through a real isolated check, show, and failures command sequence.

## Notes

[2026-11-19T19:41:58Z · sase-1tc.5.1.2] VERIFIED candidate_projection. Rust: new sase_core::bead::triage_owners (policy + replay lane) and bead::read_model::triage_owners (indexed lane: issue_type/task_type/created_at columns + json_extract of title, closed_at, task_type_fields.node_id/location; no IssueWire decode). Binding bead_triage_owner_candidates(beads_dir, now_ts=None) releases the GIL; registered, round-trip tested, added to REQUIRED_BINDINGS. Python: bead_read_facade.triage_owner_candidates (require_rust_binding, no fallback); gather_owner_candidates now only resolves the store and transports candidates+diagnostics, honors now_ts, fails open; locator contract (bare stage label like "lint (symvision)" unsupported) documented. No candidate cap; 1s slice and 5s budget unchanged. Tests: Rust 8 triage_owners (policy, every status, recent/edge/expired/unknown/garbled/naive closes, now_ts, node-over-location, cached==replay with store_io_stats reads/snapshot_loads/full_replays all 0, five-key wire, classifier wire + match_owners, stage-label negative) + 1 binding round-trip; Python 10 in tests/tool/test_triage_owner_candidates.py (matches retired Python policy at 4 now_ts values, no Python hydration with list_issues/issue_from_dict/issues_from_list patched to raise, missing store, binding raise, diagnostics, stage-label settle negative) + 2 new executor regressions (unavailable store diagnostic keeps exit 9; stored owner survives empty-gather re-settle) + existing timeout regression. CLI acceptance (tests/tool/test_triage_owner_cli_acceptance.py, real subprocess sase tool run check -> tool runs -j -> tool show -j -> tool failures -t check -j, isolated SASE_HOME and cache-backed event store, real tools/run_silent + failing pytest, nothing mocked): failing node tests/test_owner_probe.py::test_owner, fixture owner fx-1; stage-first run 3ce7c0e8fcf8edc9d1e9647c81a20a3f exit 1, decision stop/known; fresh-settle run 6615bbcdcafb7956a93a78af0df05489 exit 1, decision stop/never; both class unknown with label.possible_owners == newest_owners == [{id: fx-1, status: open, reason: possible owner, matched_on: location}]. Fixture dirs removed; live ledger untouched.

[2026-11-19T19:42:06Z · sase-1tc.5.1.2] TIMINGS (gather_owner_candidates, same stores, old = global sase 0.44.x Python hydration, new = local rebuilt binding). Live store (1,476 tasks, 309 candidates): old warm median 0.252-0.272s (max 0.29s); new warm median 0.146s (max 0.231s), of which binding 0.102s and store resolution 0.005s. Large fixture /tmp (2,374 tasks, 2,136 closed history, each ~25KB description+notes+design, 141 candidates): old warm median 0.237-0.664s with a 2.706s outlier over the 1s slice; new warm median 0.063s (max 0.079s), binding 0.053s. COLD-PATH LIMIT: the first read after a read-model invalidation (e.g. crate-version change) rebuilds the cache: 11.8s on the large fixture and 1.3s on the live store (old path cold was 9.7s on live). A cold rebuild cannot fit the unchanged 1s slice: the outer bounded gatherer times out and the run records the "owner candidates timed out" diagnostic with no owners (fail-open, exit code unchanged); later warm runs attach owners. Gates: sase-core sase tool run check run b76b98e69b07ba8289a7b13aa3d7ccf4 exit 0. sase sase tool run check run 203b10da45bc5567b16d396fbb323c64 exit 1: every lint stage passed; test (scoped) escalated to the full suite, 62,152 passed, 12 failed, none in changed/new tests: 4 KNOWN; 6 NEW load flakes that pass in isolation (tests/fakey/test_runner_slots_e2e.py x4, tests/fakey/test_gate_capacity_custom_e2e.py, tests/pager/test_view_leak.py); 2 NEW deterministic failures that reproduce identically on clean base c756511c11 (stash check): test_macro_string_literals_avoid_xprompt_terms and test_artifact_directory_operation_sites_are_reviewed. Core pin: a declaration committing both repos lets the host write the pushed core SHA into sase-core-revision.txt; local Python validated against the rebuilt binding (source identity head 5ad60139 + dirty 007cd131).

[2026-11-19T19:42:24Z · sase-1tc.5.1.2] PROPOSED FOLLOW-UP: test_macro_string_literals_avoid_xprompt_terms is red again on base c756511c11 — tests/turns/test_workspace_retention_agents_scratch.py carries the string literals "%xprompts_enabled:false" and "%xprompts_enabled:true" outside _MACRO_STRING_ALLOWLIST; sase-1hr tracked the same symptom but was closed 2026-11-17 as obsolete, so it needs reopening or a new ci task.

[2026-11-19T19:42:31Z · sase-1tc.5.1.2] PROPOSED FOLLOW-UP: test_artifact_directory_operation_sites_are_reviewed fails on base c756511c11 — src/sase/agents_sync/publication_scratch.py:sweep_publication_scratch (added by c756511c11 feat(agents-sync): reserve 15s for publisher drain cleanup) is an unreviewed artifact-directory operation site missing from the audit allowlist; no bead tracks it.

[2026-11-19T19:42:37Z · sase-1tc.5.1.2] PROPOSED FOLLOW-UP: full-lane load flakes seen in sase run 203b10da45bc5567b16d396fbb323c64 that all pass in isolation — tests/fakey/test_runner_slots_e2e.py (test_child_is_exempt_while_repeat_roots_stay_capped, test_crashed_fakey_runner_frees_slot_without_done_marker, test_fakey_agents_respect_cap_and_release_in_fifo_order, test_fakey_priority_admission_differs_from_park_order; fakey exit 124 timeouts) have no owner; test_gate_capacity_custom_e2e and test_view_leak are already covered by sase-1q8 and sase-1ps.

[2026-11-19T19:42:52Z · sase-1tc.5.1.2] Candidate projection moved to Rust (bead::triage_owners + indexed read-model lane, binding bead_triage_owner_candidates, required, GIL released); gatherer now transports only candidate fields and diagnostics, with now_ts honored and fail-open behavior kept. Verified: 8 Rust + 1 binding tests, 10 Python facade/gatherer tests that match the retired Python policy with no Python hydration, 2 new executor regressions, and a real subprocess CLI acceptance (stage-first run 3ce7c0e8… and fresh-settle run 6615bbcd…, both exit 1, owner fx-1 matched_on location in both possible_owners and newest_owners). Warm gather: large fixture 0.24-0.66s down to 0.063s; live 0.25s down to 0.146s. A cold read-model rebuild still exceeds the 1s slice and fails open. sase-core check b76b98e6 exit 0; sase check 203b10da exit 1 with only non-change failures (6 load flakes pass isolated, 2 reproduce on clean base c756511c11, 4 KNOWN), recorded as PROPOSED FOLLOW-UPs.

## Dependencies

- **Depends on:** [sase-1tc.5.1.1](sase-1tc.5.1.1.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.5.1.2/README.md) | [sase-1tc.5.1.2](sase-1tc.5.1.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cb76eb2`](https://github.com/sase-org/sase-core/commit/cb76eb283d319c24c3eb8ecd305f4f6eba3d604f) | feat(bead): project triage owner candidates from the read model | [sase-1tc.5.1.2](sase-1tc.5.1.2.md) | 2026-11-19 14:44:43 EST |
| sase | [`179495b`](https://github.com/sase-org/sase/commit/179495b93a9650f8f18ae1d8511af8e4bdb7e5a3) | feat(triage): load owner candidates through the Rust bead projection | [sase-1tc.5.1.2](sase-1tc.5.1.2.md) | 2026-11-19 14:46:40 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.5.1.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.5.1.2/README.md

<!-- sase:referenced-by:end -->

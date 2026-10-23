# Bead: sase-1n6.5.1.5.2.1.1 — Clear the three blockers between master and a live rehearsal

[Bead Pages](../README.md) / [sase-1n6.5.1.5.2.1](sase-1n6.5.1.5.2.1.md) / sase-1n6.5.1.5.2.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12n.md) · **Assignee:** `sase-1n6.5.1.5.2.1.1` · **Size:** medium
**Created:** 2026-10-20 15:25:39 EDT · **Closed:** 2026-10-20 16:38:26 EDT
**Plan:** [202610/deployed\_qualification\_proof.md](https://github.com/sase-org/sase--plans/blob/main/202610/deployed_qualification_proof.md)

## Description

unblock: grant actions:read to Full CI's reusable call behind a caller/callee permission contract test, parse sase-core's block-form EXPECTED_DIST_SUFFIXES through the shared _release_core parser, refresh the stale contract manifest, and replay the rehearse build and published-core steps locally against real inputs.

## Notes

[2026-10-20T19:49:19Z · sase-1n6.5.1.5.2.1.1] Unblock complete on origin/master aae7eae667 (no prior fix of A/B/C).

Blocker A — Full CI permissions:
- .github/workflows/full.yml now grants contents:read and actions:read (callee ci.yml cannot exceed the caller grant).
- Generic reusable-caller contract in tests/_github_actions_ci_helpers.py: every local uses: ./.github/workflows/<callee>.yml job must explicitly grant every scope the callee declares (workflow ∪ jobs; write covers read; missing explicit map fails).
- Live scan is green. Old full.yml {contents:read} fails on actions:read. Named passes: release.yml qualify-ci → ci.yml, ci.yml → build-core.yml, telemetry.yml → build-core.yml.
- actionlint .github/workflows/full.yml: clean.

Blocker B — suffix parser:
- tools/release_candidate.parse_expected_suffixes now loads tools/_release_core.py by path (stdlib-only, same as _release_qualification) and maps CoreEnsureError → Refusal, returning list.
- Shared block-form regex now matches any indent so jobs/env fixtures and sase-core's top-level env block both parse; empty and duplicate blocks refuse.
- core-suffixes --file against real sase-core tags:
  - v0.42.0 and v0.41.0 emit the five suffixes: manylinux_2_28_x86_64.whl, manylinux_2_28_aarch64.whl, universal2.whl, win_amd64.whl, .tar.gz
  - v0.34.48 refuses: REFUSED cannot find EXPECTED_DIST_SUFFIXES in .github/workflows/release-plz.yml (exit 2)

Blocker C — contract manifest:
- just refresh-contract-manifest wrote 87 files.
- Dropped non-collected facade tests/test_release_candidate.py; admitted tests/test_github_actions_release_steward.py, tests/test_release_candidate_inventory.py, tests/test_release_candidate_rerun.py, tests/test_release_candidate_seal.py.
- _MANIFEST_ENTRY_BUDGET = 87. tests/test_contract_manifest.py passes.

Local rehearse replay (temp /tmp/sase-1n6-unblock-replay-V353wX, no GitHub mutation, no repo dist/):
- uv build --out-dir: sase-0.18.0-py3-none-any.whl + sase-0.18.0.tar.gz
- core-files --version 0.42.0 --lock uv.lock: 5 live files
- seal + verify: OK candidate-5c7234f8b79f5c494247d40313fbab17 (core_version 0.42.0)
- published-core 0.42.0: sase_core_rs-0.42.0-cp312-abi3-manylinux_2_28_x86_64.whl (sha256 c26d3d23780e261ef0d8b40bf954bb3a61b10197b8d9978184b33b0a966f8a0f, probe=false)
- published-core --probe-version 0.41.0 with 0.41.0 files/suffixes: sase_core_rs-0.41.0-cp312-abi3-manylinux_2_28_x86_64.whl (sha256 5f76bfdc4bbd25a891c79efe3c6f4dff7ea07336dab36fe9aefa9d8416e79c6b, probe=true, probe-core-version.txt=0.41.0)
- uv run --no-project --isolated --with sase-core-rs==0.42.0 python tools/check_sase_core_rs_bindings: exit 0, "sase_core_rs 0.42.0 exposes all 866 bindings"
- same with sase-core-rs==0.41.0: exit 1, missing 1 of 866: mobile_pairing_issue

Confirmed probe: 0.41.0. Intended/sealed core stays 0.42.0. Next phase (live-proof) should dispatch rehearse, rehearse with -f probe_core_version=0.41.0, and Full CI at one SHA once this commit is on remote master.

Focused tests passed: test_github_actions_ci_master_gate, test_github_actions_ci_workflow, test_github_actions_release, test_github_actions_build_core, test_github_actions_setup_sase, test_release_candidate_seal/published_core/qualify_red, test_release_core, test_contract_manifest. sase bead epic-symbols: none. just fix clean.

[2026-10-20T20:38:07Z · sase-1n6.5.1.5.2.1.1--1] PROPOSED FOLLOW-UP: TUI app import budget remains over cap — just check ToolRun c17e89cb13d5d21da56efc0273ba142a classified tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget as KNOWN (3522 modules vs 3522 cap, touched=false, 34 agents / 6 workspaces); already tracked by sase-1ic.

[2026-10-20T20:38:13Z · sase-1n6.5.1.5.2.1.1--1] PROPOSED FOLLOW-UP: no_ref_prefix_dispatch flake on util/imported_revision.py — same ToolRun classified tests/ace/tui/artifacts_contract/test_no_ref_prefix_dispatch.py::test_behavioral_modules_do_not_dispatch_on_ref_prefix as FLAKY from tests/reproducible_flake_baseline.txt@aae7eae66779 (touched=false, offender util/imported_revision.py); same test node as sase-174.

[2026-10-20T20:38:26Z · sase-1n6.5.1.5.2.1.1--1] Cleared the three master-to-rehearsal blockers: Full CI now grants actions:read (reusable-caller contract green), parse_expected_suffixes reads sase-core block-form EXPECTED_DIST_SUFFIXES via shared _release_core, contract manifest refreshed to 87. Local rehearse replay sealed 0.42.0 and probed 0.41.0. sase bead epic-symbols: none. just check ToolRun c17e89cb13d5d21da56efc0273ba142a verdict no_new_failures (KNOWN sase-1ic import budget 3522/3522, FLAKY sase-174 no_ref_prefix_dispatch); both pre-existing and recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1n6.5.1.5.2.1.2](sase-1n6.5.1.5.2.1.2.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.5.1.5.2.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.1.5.2.1.1.md) | [sase-1n6.5.1.5.2.1.1](sase-1n6.5.1.5.2.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3db3b51`](https://github.com/sase-org/sase/commit/3db3b51d5362c8c3fd9485e6452b48d910624300) | fix(ci): grant Full CI actions:read and parse core suffix blocks | [sase-1n6.5.1.5.2.1.1](sase-1n6.5.1.5.2.1.1.md) | 2026-10-20 16:40:43 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:13d][1] | Research which agents stalled the sase-1n6 epic: unblock epic and its phases | 1 |
| read-by | [agent:sase-1n6.5.1.5.2.1.1--1][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.13d/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.1.5.2.1.1.md

<!-- sase:referenced-by:end -->

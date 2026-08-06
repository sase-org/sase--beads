# Bead: sase-fp.2 — Curated contract/audit test set

[Bead Pages](../README.md) / [sase-fp](README.md) / sase-fp.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tn/README.md) · **Assignee:** `sase-fp.2` · **Size:** small
**Created:** 2026-08-05 20:56:08 EDT · **Closed:** 2026-08-05 22:00:21 EDT
**Plan:** [202608/test\_suite\_tier1.md](https://github.com/sase-org/sase--plans/blob/main/202608/test_suite_tier1.md)

## Description

contract: add the `contract` pytest marker, curate the repository-wide audit tests behind it to a measured serial-runtime budget, generate a committed manifest from the marker, and add drift and budget guards.

## Notes

[2026-08-06T01:39:32Z · sase-fp.2] PROPOSED FOLLOW-UP: contract-set budget margin -- test_suite_gate_integration.py (~3.6s) and test_markdown_template_packaging.py (~1.3-1.7s, invokes `uv build`) are legitimate no-import-edge-can-express audits but were curated OUT of the committed contract set purely to keep serial runtime margin under the 30s hard budget (final measured ~24-26s for 29 files, wrapper-included, under real host contention from concurrent workspaces). Revisit when the runner phase (sase-fp.3) adds its promised zero-token scoped-run integration test to test_suite_gate_integration.py per the epic plan -- that is the natural point to re-measure and decide whether either file should rejoin the set, possibly by swapping out a lower-value item.

[2026-08-06T02:00:21Z · sase-fp.2] Verified all deliverables from plans/202608/test_suite_tier1.md's `contract` phase: contract marker registered in pyproject.toml, applied to 29 curated files, tests/contract_manifest.txt generated, just refresh-contract-manifest recipe added and exercised, drift guard + budget guard added in tests/test_contract_manifest.py.

Found and fixed a real bug during verification: the nested pytest subprocess these two guards spawn inherits the exact same TMPDIR (tools/run_pytest derives it deterministically from the repo path) as the enclosing `just test` run, so its own tmp-leak-guard session hook raced against concurrently-running sibling xdist workers and produced false-positive "system temp leakage" failures under `just test`. Reproduced twice, fixed by disabling SASE_TMP_LEAK_GUARD_DISABLED for the nested subprocess in tools/refresh_contract_manifest and tests/test_contract_manifest.py (the enclosing session's own guard still catches any real leak across the nested subprocess's lifetime).

Ran full `just test` three times after the fix: contract manifest tests passed cleanly each time (19-29s, under the 30s hard budget). Two unrelated pre-existing tests (test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout, ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version) flaked once each under this host's heavy concurrent-workspace contention (load avg ~25/64 cores) but pass cleanly in isolation -- unrelated to this phase's changes. All other just check gates pass: ruff, ruff format, mypy (2750 files), pyscripts, changelog, toobig, keep-sorted, sase validate, validate-committed-plans. symvision fails on a pre-existing unrelated finding (progress_fingerprint in commit_finalizer_git.py, tracked as sase-fj).

## Dependencies

- **Blocks:** [sase-fp.3](sase-fp.3.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fp.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fp.2/README.md) | [sase-fp.2](sase-fp.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ab955c9`](https://github.com/sase-org/sase/commit/ab955c9cac1021c77c736ddeda9b499444c7d530) | test: curate repository-wide audit tests behind a \`contract\` pytest marker | [sase-fp.2](sase-fp.2.md) | 2026-08-05 22:01:52 EDT |

# Bead: sase-fp.8.1 — Load- and machine-normalized contract-set budget guard

[Bead Pages](../README.md) / [sase-fp.8](sase-fp.8.md) / sase-fp.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-fp.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fp.land/README.md) · **Assignee:** `sase-fp.8.1` · **Size:** medium
**Created:** 2026-08-06 01:41:42 EDT · **Closed:** 2026-08-06 02:14:40 EDT
**Plan:** [202608/test\_selection\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/test_selection_landing.md)

## Description

budget: replace the wall-clock ceiling in test_contract_set_serial_runtime_stays_within_budget with a calibration-probe-normalized CPU measurement, so the guard bounds the contract set's size instead of the host's load, and settle sase-fp.2's deferred contract-set membership question with the re-measured headroom.

## Notes

[2026-08-06T06:14:13Z · sase-fp.8.1] PROPOSED FOLLOW-UP: Make test_contract_manifest_matches_marker_selection cheaper — its whole-repo `--collect-only` measured 32.4s on the dev host at HEAD (plan estimated ~21s), so tests/test_contract_manifest.py now costs ~58s of every full-suite run, more than the contract set it guards.

[2026-08-06T06:14:40Z · sase-fp.8.1] Replaced the wall-clock ceiling in test_contract_set_serial_runtime_stays_within_budget with a calibration-probe-normalized child-CPU measurement. New tests/_test_contract_budget.py holds the probe (fixed pure-Python loop + sha256 + 20 subprocess spawns; PROBE_BASELINE_CPU_SECONDS=0.77 measured on the 64-core dev host), resource.getrusage(RUSAGE_CHILDREN) deltas around subprocess.run, the pure normalization arithmetic, and the diagnostic failure message (raw wall, raw child CPU, both probe readings, factor, normalized figure). The nested run is bracketed by one probe before and one after and their mean is used. resource is Unix-only and nothing else in the repo imports it, so the guard is skipif(not HAVE_RESOURCE) rather than an ImportError at collection. _BUDGET_SECONDS stays 30.0; the comment now records the 2026-08-06 dev-host measurement (34 files, 289 tests, 22.6-23.2s normalized, ~7s headroom, holding to within 7% while raw wall moved 24s->42s). tests/test_contract_budget_normalization.py unit-tests the arithmetic over injected numbers without running the contract set, including the measured quiet vs 96-spinner pair as a regression case. Settled sase-fp.2's deferred membership question: both candidates stay out and the guard comment records why — test_suite_gate_integration.py costs +4.8s normalized (17% of the budget) and test_markdown_template_packaging.py +2.0s, while every change that could break either (tests/_suite_gate.py, tools/run_pytest, pyproject.toml) already forces the full suite through the broadening rules. VERIFIED: just install; the guard and the normalization suite pass standalone (14 passed); the guard passes under 96 spinner processes on 64 cores where its own inner wall clock read 42.8s, i.e. where the old 30s wall assertion would have failed; every check-full lint gate green (fmt-py, fmt-md, keep-sorted, ruff, mypy, pyscripts, changelog, symvision, toobig, validate, validate-committed-plans); two full 'just test' runs, the guard passing inside both — run 1 was 1 failed/25824 passed with the sole failure being the known load-sensitive flake tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout (already the land phase's follow-up 6, untouched by this change), and run 2 was fully green at 25825 passed/7 skipped. Recorded one PROPOSED FOLLOW-UP: the sibling guard test_contract_manifest_matches_marker_selection measured 32.4s (plan estimated ~21s), making that module ~58s of every full-suite run.

## Dependencies

- **Blocks:** [sase-fp.8.3](sase-fp.8.3.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fp.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fp.8.1/README.md) | [sase-fp.8.1](sase-fp.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3e86001`](https://github.com/sase-org/sase/commit/3e8600168e4845566525836546e81cbadc5fbfe4) | test: normalize the contract-set budget guard against a calibration probe | [sase-fp.8.1](sase-fp.8.1.md) | 2026-08-06 02:15:26 EDT |

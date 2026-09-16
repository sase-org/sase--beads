# Bead: sase-11e.8.6.4 — Align the CI core pin and prove the combined upgrade contract

[Bead Pages](../README.md) / [sase-11e.8.6](sase-11e.8.6.md) / sase-11e.8.6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11e.8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11e.8.land.md) · **Assignee:** `sase-11e.8.6.4` · **Size:** medium
**Created:** 2026-09-16 06:01:38 EDT · **Closed:** 2026-09-16 09:24:48 EDT
**Plan:** [202609/routine\_job\_final\_contract\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/routine_job_final_contract_repairs.md)

## Description

acceptance: integrate the actual pinned Rust dependency, add missing production-path acceptance, review drift, and run complete repository verification.

## Notes

[2026-09-16T13:24:48Z · sase-11e.8.6.4] Pinned sase-core-revision.txt to 51c7c38d6d1192fad0a3c807cc233b7ccdcb1acf; added routine/job upgrade fixture covering legacy/public config, list/doctor/run/status/history/env/linkage paths. Verified: just rust-install; tools/check_sase_core_rs_bindings; tools/validate_sase_core_rs; tools/validate_sase_core_rs_version; tools/probe_core_floor --advisory (blocked_unpublished advisory); .venv/bin/python -m pytest -q tests/test_axe_cli.py::test_routine_job_upgrade_contract_exercises_public_and_legacy_paths; just check; linked sase-core just check with PYO3_PYTHON+LD_LIBRARY_PATH.

## Dependencies

- **Depends on:** [sase-11e.8.6.3](sase-11e.8.6.3.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11e.8.6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11e.8.6.4/README.md) | [sase-11e.8.6.4](sase-11e.8.6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c9d047`](https://github.com/sase-org/sase/commit/8c9d04759bb441d99211d0be1f4afb7698032012) | test(axe): verify routine job core upgrade contract | [sase-11e.8.6.4](sase-11e.8.6.4.md) | 2026-09-16 09:26:39 EDT |

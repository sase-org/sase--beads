# Bead: sase-zw.8.7.3 — Preserve run protections through deletion and empty-shard cleanup

[Bead Pages](../README.md) / [sase-zw.8.7](sase-zw.8.7.md) / sase-zw.8.7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zw.8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.8.land.md) · **Assignee:** `sase-zw.8.7.3` · **Size:** medium
**Created:** 2026-09-14 16:48:13 EDT · **Closed:** 2026-09-15 11:14:00 EDT
**Plan:** [202609/disk\_retention\_final\_safety.md](https://github.com/sase-org/sase--plans/blob/main/202609/disk_retention_final_safety.md)

## Description

runs: fix symlink-ancestor validation, protect empty referenced runs, refresh protection coverage safely, and expose deduplicated actionable previews.

## Notes

[2026-09-15T14:21:02Z · sase-zw.8.7.3] PROPOSED FOLLOW-UP: Stabilize empty-home git identity subprocess in full-suite runs — main just check failed tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess once after unrelated retention changes, then the same test passed when rerun singly with LD_LIBRARY_PATH set.

[2026-09-15T15:14:00Z · sase-zw.8.7.3] Implemented run-retention schema v2 protections, symlink/invalid-path safety, protected empty-shard preservation, preview budget parity, and deduplicated artifact_run_prune report notifications. Verified cargo test -p sase_core agent_artifact_run_retention; just rust-install into workspace venv; focused pytest tests/core/test_agent_artifact_run_retention.py tests/test_axe_chop_output_contract_retention.py; linked core just check with LD_LIBRARY_PATH; main just check with LD_LIBRARY_PATH.

## Dependencies

- **Depends on:** [sase-zw.8.7.2](sase-zw.8.7.2.md) ✓ · ⧖ 2026-09-14
- **Blocks:** [sase-zw.8.7.4](sase-zw.8.7.4.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.8.7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.8.7.3/README.md) | [sase-zw.8.7.3](sase-zw.8.7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`53c6c51`](https://github.com/sase-org/sase/commit/53c6c51c3b09ad33239c581d138fc94cff1205cc) | fix(retention): preserve protected artifact runs | [sase-zw.8.7.3](sase-zw.8.7.3.md) | 2026-09-15 11:16:11 EDT |

# Bead: sase-n8.3 — Python wire mirror, facade call, and skew probes

[Bead Pages](../README.md) / [sase-n8](README.md) / sase-n8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.3` · **Size:** medium
**Created:** 2026-08-16 11:31:32 EDT · **Closed:** 2026-08-16 13:35:39 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

wire: mirror the new core contract on the Python side — alias trail/origin on the marker wires, a new agent_alias_history_wire module with its to_dict/from_dict helpers, a `query_agent_alias_history` facade function under the artifact-index operation lock — and extend the sase_core_rs validator so a stale wheel fails loudly instead of returning empty history.

## Notes

[2026-08-16T17:35:39Z · sase-n8.3] Verified: just lint passes (ruff, mypy, symvision with new epic-symbol whitelist, terminology/line-count audits); just check's full run (31151 tests) had 2 failures (test_config_center_state.py::test_save_atomically_replaces_existing_state, test_config_cache.py::test_first_config_token_read_does_not_start_worker) that are unrelated to this diff and pass cleanly in isolation — resource contention from concurrent agent workspaces on this host. All new/modified wire tests (tests/core/test_agent_alias_history_wire.py, test_agent_output_variable_history_wire.py, test_core_agent_scan_wire.py) pass against the rebuilt sase-core-rs 0.27.14 wheel. tools/validate_sase_core_rs (including the new schema-22 alias-history probe) exits 0.

## Dependencies

- **Depends on:** [sase-n8.2](sase-n8.2.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n8.5](sase-n8.5.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.3/README.md) | [sase-n8.3](sase-n8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`57c71d1`](https://github.com/sase-org/sase/commit/57c71d17a007e73b016a6cac60d14698c45c9b53) | feat(core): mirror alias-history wire contract and add skew probe | [sase-n8.3](sase-n8.3.md) | 2026-08-16 13:37:24 EDT |

# Bead: sase-11l.5.1.2.1.2 — Python hold facade and launch-hold primitives

[Bead Pages](../README.md) / [sase-11l.5.1.2.1](sase-11l.5.1.2.1.md) / sase-11l.5.1.2.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.5.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.2.md) · **Assignee:** `sase-11l.5.1.2.1.2` · **Size:** medium
**Created:** 2026-09-16 16:01:38 EDT · **Closed:** 2026-09-17 07:27:10 EDT
**Plan:** [202609/hold\_launch\_arming.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_launch_arming.md)

## Description

hold-facade: extend the facade with an explicit armer and selectors, rebind, a shared TTL resolver, and `launch`-kind validation and liveness (a receipt only counts once it is complete). Add `launch_hold.py` with the key, armer, arm, pre-arm, rebind, re-anchor, and release primitives, plus `HOLD_ARMER_WAIT_PRIORITY`. The CLI reuses the TTL resolver.

## Notes

[2026-09-17T11:26:30Z · sase-11l.5.1.2.1.2] PROPOSED FOLLOW-UP: tests/test_proc_env_isolation.py::test_sase_ml_file_families_ignore_inherited_live_proc_env fails on master (pre-existing, unrelated to this phase) — its _SASE_ML_FILE_FAMILIES list still references "tests/test_config.py::test_deep_merge_list_concatenation", but tests/test_config.py no longer exists after commit 99764a3fc7 (test(config): split config tests by area). Update the file-family list to point at the split test file(s).

[2026-09-17T11:27:10Z · sase-11l.5.1.2.1.2] Implemented plan §5 (hold-facade): renamed _agent_armer_wire -> public agent_armer_wire_for_artifacts(pid_fallback=); arm_agent_hold gained armer/selectors kwargs (pending merges into selectors[artifact_dirs], dropping the armer's own agent artifacts dir); added rebind_agent_hold and resolve_hold_ttl_seconds to agent_hold_facade.py (cli_hold._resolve_ttl_seconds now delegates to it, unchanged messages); agent_hold_store._validate_hold_record and agent_hold_liveness now accept/evaluate the launch armer kind (pid_alive via _pid_alive or started.json fallback through is_process_running; done_marker_present treats receipt.json specially, requiring complete:true). Added new src/sase/agent/launch_hold.py with LAUNCH_HOLD_KEY_ENV, LAUNCH_HOLD_RELEASE_REASON, LaunchHoldError, unit_hold_key, hold_fields_for, arm_hold_for_fields, rebind_hold, release_hold_best_effort, launch_unit_armer, and runner_anchor_armer (no call sites yet, as specified). Added HOLD_ARMER_WAIT_PRIORITY=5 to core/runner_slots. CLI's hold show now prints 'Done marker:'. Verified: just check is green (only pre-existing, unrelated failure in tests/test_proc_env_isolation.py, noted as a PROPOSED FOLLOW-UP); just lint, fmt-py-check, mypy, ruff, and validate all pass; symvision passes via 9 new --epic-symbol entries in the Justfile keyed to the still-open parent epic sase-11l.5.1.2.1 for the primitives that typed-arm/bootstrap-arm will wire up; sase bead epic-symbols sase-11l.5.1.2.1.2 shows no entries keyed to this phase bead.

## Dependencies

- **Depends on:** [sase-11l.5.1.2.1.1](sase-11l.5.1.2.1.1.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11l.5.1.2.1.3](sase-11l.5.1.2.1.3.md) ◐ · ⧖ 2026-09-16
- **Blocks:** [sase-11l.5.1.2.1.4](sase-11l.5.1.2.1.4.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.5.1.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.5.1.2.1.2/README.md) | [sase-11l.5.1.2.1.2](sase-11l.5.1.2.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`02f0fd3`](https://github.com/sase-org/sase/commit/02f0fd3893f57267a0bef8f6f69fc23adc89c675) | feat(agent-hold): add launch-hold facade primitives and launch armer kind | [sase-11l.5.1.2.1.2](sase-11l.5.1.2.1.2.md) | 2026-09-17 07:28:41 EDT |

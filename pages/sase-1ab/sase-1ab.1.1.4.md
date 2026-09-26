# Bead: sase-1ab.1.1.4 — Editor text, classification, and cross-repo check

[Bead Pages](../README.md) / [sase-1ab.1.1](sase-1ab.1.1.md) / sase-1ab.1.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ab.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.1.md) · **Assignee:** `sase-1ab.1.1.4` · **Size:** small
**Created:** 2026-09-26 00:28:18 EDT · **Closed:** 2026-09-26 02:52:16 EDT
**Plan:** [202609/sase\_core\_turn\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_turn_expand.md)

## Description

sweep: retarget the editor proc snippet, classify every remaining shell hit, and prove a sase workspace rebuilt against this core passes check with no sase source changes.

## Notes

[2026-09-26T06:31:42Z · sase-1ab.1.1.4] PROPOSED FOLLOW-UP: contract-flip must flip pinned legacy spellings — agent_scan/wire.rs agent_session_shell+shell_kind keys; scanner.rs 3-key/2-key fallbacks and monitor-to-proc map; index/storage.rs gate_shell_id column+index and GATE_TURN_INDEX_COLUMN; procs/wire.rs+store.rs shell_name/shell_kind keys, proc-shell lifecycle/origin, shell: conflict prefix and shell_name field; agent_launch invalid-proc-shell-name diagnostic; agent_hold proc_shell key and match kind; runner_capacity 3 agent_session_shell_* keys; fleet status agent_shell/historical_shell; locators shell_id key, shell: segment and shell-<hex> ids; owner facts shell_start/stop_status; catalog safe_identifier shell emit; legacy bindings find_gate_shell_by_gate_id and validate_standalone_proc_shell_name

[2026-09-26T06:31:55Z · sase-1ab.1.1.4] PROPOSED FOLLOW-UP: wire-cutover must switch sase readers to new bindings — agent_scan_facade.find_gate_shell_by_gate_id (callers: completion/candidates/catalog_plans.py, ace/tui/actions/agents/_notification_delta_dirs.py, _notification_gate_refresh.py, gate_shell/store.py, _plan_approval_response.py) and agent_launch_facade.validate_standalone_proc_shell_name (caller: agent/launch_proc_runtime.py)

[2026-09-26T06:32:05Z · sase-1ab.1.1.4] PROPOSED FOLLOW-UP: runtime-cutover owns the sase-side gate-shell vocabulary (docs, gate_shell package, TUI strings) still asserted by sase tests; core kept every emitted string byte-identical so sase passes unmodified

[2026-09-26T06:52:16Z · sase-1ab.1.1.4--2] Editor-text sweep done: retargeted editor proc snippet and classified remaining shell hits to turn vocabulary (comments, test names, locals only; no wire/behavior change). just check green (exit 0, 6m37s and 6m10s runs); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1ab.1.1.3](sase-1ab.1.1.3.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.1.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.1.1.4.md) | [sase-1ab.1.1.4](sase-1ab.1.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6953a96`](https://github.com/sase-org/sase-core/commit/6953a96460eec45bb46fe8a505304626bd375708) | refactor(core): retarget editor text and classify remaining shell hits to turn vocabulary | [sase-1ab.1.1.4](sase-1ab.1.1.4.md) | 2026-09-26 02:52:52 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ab.1.1.4--2][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1ab.1.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.1.1.4.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.1.1.land/README.md

<!-- sase:referenced-by:end -->

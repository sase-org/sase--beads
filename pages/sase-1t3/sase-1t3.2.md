# Bead: sase-1t3.2 — Executor-saturation gauge and telemetry retention

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.2` · **Size:** small
**Created:** 2026-11-16 07:57:54 EST · **Closed:** 2026-11-16 08:56:20 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

telemetry-guardrails: add a default-executor saturation gauge to the existing memory heartbeat, keep at least 24 h of tui_stalls rows, and cap the unbounded tui_trace file with rotation.

## Notes

[2026-11-16T13:56:20Z · sase-1t3.2--2] telemetry-guardrails verified and complete.

Landed: default-executor saturation fields on the existing memory heartbeat (`default_executor_workers/threads/queue_depth/saturated`); tui_stalls.jsonl prune retains at least 24h (48h cutoff, hourly prune bucket); tui_trace.jsonl now rotates via append_jsonl_record (default 10x bounded-log max, override SASE_TUI_TRACE_MAX_BYTES).

Verification: `just fmt` succeeded; `sase tool run check` 6274a4c67e72e8de6a5c639ed4c81b5f succeeded (exit 0, monitor vk1vgdevzxq9, triage pass, KNOWN 0, FLAKY 0). Stages green including fmt, lint (ruff/mypy/symvision/docs), SASE validation, and scoped tests escalated to the full suite (core-identity-changed). `sase bead epic-symbols sase-1t3.2` reported no remaining --epic-symbol entries. No PROPOSED FOLLOW-UP: the check did not fail.

## Dependencies

- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.9](sase-1t3.9.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.2.md) | [sase-1t3.2](sase-1t3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c580b68`](https://github.com/sase-org/sase/commit/c580b689c18bace8e59234042fcbe08d9bfe2b23) | feat(ace): add executor saturation gauge and telemetry retention | [sase-1t3.2](sase-1t3.2.md) | 2026-11-16 08:58:50 EST |

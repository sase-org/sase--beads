# Bead: sase-xe.16.11.7.5 — Rebuild ACE's remote projection on published core contracts

[Bead Pages](../README.md) / [sase-xe.16.11.7](sase-xe.16.11.7.md) / sase-xe.16.11.7.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0hv](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0hv.md) · **Assignee:** `sase-xe.16.11.7.5` · **Size:** medium
**Created:** 2026-09-09 15:49:30 EDT · **Closed:** 2026-09-09 22:42:02 EDT
**Plan:** [202609/unified\_agents\_across\_machines.md](https://github.com/sase-org/sase--plans/blob/main/202609/unified_agents_across_machines.md)

## Description

unified-projection: ratchet to the published core, replace Python normalization and counting with bindings, merge remote rows into the pure shared pipeline, and add the machine query field and grouping.

## Notes

[2026-09-10T02:08:42Z · sase-xe.16.11.7.5] PROPOSED FOLLOW-UP: Flaky test: tests/test_clan_summary_script_execution.py::test_timed_out_summary_script_escalates_to_sigkill_when_sigterm_is_ignored failed during full just check, then passed on immediate single-test rerun.

[2026-09-10T02:42:02Z · sase-xe.16.11.7.5] Verified with just install, just fmt, focused fleet/query/grouping/model-shortcut suite (419 passed), just check (full-suite escalation passed), and epic-symbols showing no leftovers.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.1](sase-xe.16.11.7.1.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-xe.16.11.7.10](sase-xe.16.11.7.10.md) ✓ · ⧖ 2026-09-09
- **Depends on:** [sase-xe.16.11.7.2](sase-xe.16.11.7.2.md) ✓ · ⧖ 2026-09-09
- **Depends on:** [sase-xe.16.11.7.3](sase-xe.16.11.7.3.md) ✓ · ⧖ 2026-09-09
- **Depends on:** [sase-xe.16.11.7.4](sase-xe.16.11.7.4.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-xe.16.11.7.6](sase-xe.16.11.7.6.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-xe.16.11.7.7](sase-xe.16.11.7.7.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.5/README.md) | [sase-xe.16.11.7.5](sase-xe.16.11.7.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5b330b2`](https://github.com/sase-org/sase/commit/5b330b242759f5393170cd334d19669b1236c9f1) | feat(ace): use published fleet projection contracts | [sase-xe.16.11.7.5](sase-xe.16.11.7.5.md) | 2026-09-10 01:42:38 EDT |

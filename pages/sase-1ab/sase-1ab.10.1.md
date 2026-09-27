# Bead: sase-1ab.10.1 — Legacy reader and sunset-flag repair

[Bead Pages](../README.md) / [sase-1ab.10](sase-1ab.10.md) / sase-1ab.10.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ab.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.land.md) · **Assignee:** `sase-1ab.10.1` · **Size:** medium
**Created:** 2026-09-27 08:44:26 EDT
**Plan:** [202609/sase\_turn\_rename\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename_finish.md)

## Description

reader-repair: fix the durable readers the runtime cutover corrupted (the agent_session_turn stripper, the continuation_mode and proc origin no-ops), route authored gate specs and the gate.shell config key through the flag-gated normalizers, fix the undefined LEGACY_NAMED_PROC_SECTION_ID, and audit every rename commit for more corruption, with a legacy-input test for each fix.

## Notes

[2026-09-27T13:07:32Z · sase-1ab.10.1] PROPOSED FOLLOW-UP: tests/agent/test_legacy_agent_family_syntax.py::test_gate_help_lists_only_canonical_next_fork_value still expects --next-fork {session,shell,none}; help now correctly shows {session,turn,none} — rename-stale, owned by test-repair phase (sase-1ab.10.2)

## Dependencies

- **Blocks:** [sase-1ab.10.3](sase-1ab.10.3.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1ab.10.5](sase-1ab.10.5.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.10.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.10.1.md) | [sase-1ab.10.1](sase-1ab.10.1.md) | 0 |

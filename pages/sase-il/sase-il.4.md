# Bead: sase-il.4 — Adopt tale size in sase

[Bead Pages](../README.md) / [sase-il](README.md) / sase-il.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wt](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wt/README.md) · **Assignee:** `sase-il.4` · **Size:** medium
**Created:** 2026-08-09 16:44:12 EDT · **Closed:** 2026-08-10 08:44:03 EDT
**Plan:** [202608/sase\_sizes\_memory.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_sizes_memory.md)

## Description

plan-size-adopt: raise the sase-core floor, plumb the validated tale `size` through the Python adapter, and point every remaining size instruction at the memory note.

## Notes

[2026-08-10T12:43:13Z · sase-il.4] PROPOSED FOLLOW-UP: Tighten core-owned tale size semantics — sase-core-rs 0.23.0 accepts large/xlarge tale sizes and emits tale-size-* diagnostics, while the epic design says tale size should be xsmall/small/medium only and core should own the stricter validation; this phase kept SASE launch compatibility without duplicating core accepted-size rules.

[2026-08-10T12:43:30Z · sase-il.4] PROPOSED FOLLOW-UP: Investigate escalated just check full-suite failures — just check escalated on core-identity-changed, passed lint/SASE/committed-plan gates, then the governed full pytest lane reached 99% of 28,207 items before SIGTERM with 28 cached broad failures in ACE/onboarding/publication/probe tests, preventing a clean whole-repo gate.

[2026-08-10T12:44:03Z · sase-il.4] Verified just install; just fmt; focused pytest suite for plan validation, approval, propose, committed-plan, and skill-source coverage: 100 passed; committed-plan validator passed for 3548 files after adding size: medium to archived tale plan 202608/new_task_recent_task_sweep.md; sase skill init --diff exited 0 with no diff output. just check passed lint, SASE validation, and committed-plan gates, then escalated full pytest reached 99% before SIGTERM with broad cached failures recorded as PROPOSED FOLLOW-UP.

[2026-08-10T12:45:29Z · sase-il.4] Verified focused plan validation tests passed, committed-plan validation passed, generated skill preview had no diff, and just check reached the escalated pytest lane but was terminated before a clean final result.

## Dependencies

- **Depends on:** [sase-il.2](sase-il.2.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-il.3](sase-il.3.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-il.5](sase-il.5.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-il.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.4/README.md) | [sase-il.4](sase-il.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b9008c5`](https://github.com/sase-org/sase/commit/b9008c535c4c0fd3bb4f199284c1a8369b2fd9f2) | feat(plan): normalize legacy tale size for launches | [sase-il.4](sase-il.4.md) | 2026-08-10 08:47:40 EDT |

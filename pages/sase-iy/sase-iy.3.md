# Bead: sase-iy.3 — Widen the wait-idiom gate past its receiver and name blind spots

[Bead Pages](../README.md) / [sase-iy](README.md) / sase-iy.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xb](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xb/README.md) · **Assignee:** `sase-iy.3` · **Size:** medium
**Created:** 2026-08-10 11:01:41 EDT · **Closed:** 2026-08-10 11:46:23 EDT
**Plan:** [202608/retire\_sase\_ct\_umbrella.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_sase_ct_umbrella.md)

## Description

waitgate: tools/check_test_wait_helpers only recognizes bounded-wait loops whose receiver is literally named pilot and private helpers named _wait_until, so page.pause() loops and _wait_for helpers pass it. Widen both axes and migrate every call site the widened gate reports onto the shared waiters.

## Notes

[2026-08-10T15:38:27Z · sase-iy.3] PROPOSED FOLLOW-UP: committed plan validation rejects 21 August 2026 tale plans sized large — just check is blocked at validate_committed_plans by tale-size-invalid errors in plans/202608/*.md unrelated to waitgate.

[2026-08-10T15:45:50Z · sase-iy.3] PROPOSED FOLLOW-UP: governed full test lane remains red outside waitgate — just test-scoped escalated and failed stale contract manifest, plan approval lock/model-size nodes, and agent_group_revival_e2e nodes unrelated to the widened wait gate.

[2026-08-10T15:46:23Z · sase-iy.3] Implemented widened wait-helper gate and migrated reported wait loops. Verified: .venv/bin/python tools/check_test_wait_helpers exits 0; focused pytest for checker, migrated prompt/modal/helper tests passed 141 tests; glossary navigation passed serially 7/7 and just test-contention -- tests/ace/tui/widgets/test_prompt_glossary_navigation.py reported 0 failed nodes across 3 repeats; notification cleanup tests passed 80/80; just _lint-symvision passed. just check is blocked outside waitgate at committed plan validation by 21 unrelated tale-size-invalid plan files, and just test-scoped escalated to the governed full lane with 6 unrelated failures; both were recorded as PROPOSED FOLLOW-UP notes.

[2026-08-10T15:47:20Z · sase-iy.3] Verified check_test_wait_helpers clean; focused migrated tests 141 passed; glossary serial 7 passed; glossary contention 0 failures across 3 repeats; notification tests 80 passed; just _lint-symvision passed; just check blocked by unrelated plan validation; full lane unrelated failures noted.

## Dependencies

- **Blocks:** [sase-iy.4](sase-iy.4.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-iy.5](sase-iy.5.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-iy.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-iy.3/README.md) | [sase-iy.3](sase-iy.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c49452c`](https://github.com/sase-org/sase/commit/c49452c475730db67b18ab519885924b43d61692) | test: widen test wait helper gate | [sase-iy.3](sase-iy.3.md) | 2026-08-10 11:48:33 EDT |

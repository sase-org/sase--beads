# Bead: sase-fp.7 — Two-speed verification policy in SASE memory

[Bead Pages](../README.md) / [sase-fp](README.md) / sase-fp.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tn/README.md) · **Assignee:** `sase-fp.7` · **Size:** small
**Created:** 2026-08-05 20:56:33 EDT · **Closed:** 2026-08-06 00:01:47 EDT
**Plan:** [202608/test\_suite\_tier1.md](https://github.com/sase-org/sase--plans/blob/main/202608/test_suite_tier1.md)

## Description

policy: obtain live user permission, then record the two-speed verification contract in sase/memory and regenerate the derived instruction files.

## Notes

[2026-08-06T04:01:27Z · sase-fp.7] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout failed once during a full-suite run triggered by this phase's core-identity-changed escalation (after `just install` rebuilt sase_core_rs), then passed cleanly in isolation immediately after — looks like a timing-sensitive contention flake, unrelated to this phase's doc-only change.

[2026-08-06T04:01:47Z · sase-fp.7] Live permission for the sase/memory/build_and_run.md diff was granted via Q1 (Approve as shown). Edited the canonical note to document the just check / just check-full two-speed contract (selection heuristic, tools/select_tests --explain, just selection-health) and fixed the stale Tier 0 claim that just test / just test-cov still run PNG visual snapshots. Ran sase memory init to regenerate AGENTS.md, CLAUDE.md, GEMINI.md, OPENCODE.md, QWEN.md, and sase/memory/README.md. Verified with just install then just check: all lint gates plus the scoped test lane pass green. (First just check run escalated to the full suite via the core-identity-changed rule from the just install rebuild and hit one flaky contention test, which passed cleanly in isolation and on the next just check; logged as a PROPOSED FOLLOW-UP note, not a real regression.)

[2026-08-06T04:02:30Z · sase-fp.7] Edited sase/memory/build_and_run.md per approved diff: documented the just check/just check-full two-speed verification contract and fixed the stale claim that just test/just test-cov still run PNG visual snapshots. Ran sase memory init to regenerate AGENTS.md/CLAUDE.md/GEMINI.md/OPENCODE.md/QWEN.md/sase/memory/README.md. Verified with just install + just check: markdown fmt caught one wrapping issue (fixed via just fmt + regen), then a full green run of every lint gate plus the scoped test lane.

## Dependencies

- **Depends on:** [sase-fp.4](sase-fp.4.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fp.5](sase-fp.5.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fp.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-fp.7.md) | [sase-fp.7](sase-fp.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6f1a071`](https://github.com/sase-org/sase/commit/6f1a0717f1af3ee11f757a4820822427f5489670) | docs(memory): document two-speed verification contract, fix stale visual-snapshot claim | [sase-fp.7](sase-fp.7.md) | 2026-08-06 00:03:12 EDT |

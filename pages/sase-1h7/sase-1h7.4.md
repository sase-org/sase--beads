# Bead: sase-1h7.4 — Epic-follow reducer and fact collector

[Bead Pages](../README.md) / [sase-1h7](README.md) / sase-1h7.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3v.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3v.linker.w0.md) · **Assignee:** `sase-1h7.4` · **Size:** medium
**Created:** 2026-10-06 18:17:38 EDT
**Plan:** [202610/wait\_for\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md)

## Description

reducer: add the pure sase-core reducer that maps per-member facts to AGENT/NONE/LAUNCHING/FOLLOWING/BLOCKED with the deadlock guard and the cycle hook, bind it to Python, and add the Python fact collector over the wait-dependency index. Nothing is wired into release paths yet.

## Notes

[2026-10-07T02:02:38Z · sase-1h7.4] PROPOSED FOLLOW-UP: test_identity_and_hood_waits_defer_on_stale_membership fails identically on the clean base tree (hood_confirmation.confirmed is True, expected False); unrelated to the reducer phase

## Dependencies

- **Depends on:** [sase-1h7.1](sase-1h7.1.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h7.5](sase-1h7.5.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h7.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.4.md) | [sase-1h7.4](sase-1h7.4.md) | 0 |

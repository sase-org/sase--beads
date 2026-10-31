# Bead: sase-1q5.3 — Never answer a busy index lock with a source scan

[Bead Pages](../README.md) / [sase-1q5](README.md) / sase-1q5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5k.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5k.linker.w0.md) · **Assignee:** `sase-1q5.3` · **Size:** medium
**Created:** 2026-10-30 18:38:10 EDT · **Closed:** 2026-10-30 20:04:30 EDT
**Plan:** [202610/tui\_index\_lock\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_index_lock_speedup.md)

## Description

loader-lock-busy: serve the last good tier-1 snapshot or keep the current roster when the index lock is busy, retry through existing flags, log artifact_source and repair_reason on slow loads, and document the lock's invariants.

## Notes

[2026-10-31T00:04:16Z · sase-1q5.3] PROPOSED FOLLOW-UP: tests/fakey/test_gate_capacity_custom_e2e.py::test_synchronous_gate_answer_claims_and_releases_runner_slot_capacity_like_an_agent failed in sase tool run check (abbc07ba4dbb76f4bfddf69ce97d0192) with run_gate still alive after join(_WAIT_TIMEOUT) under a loaded 37m scoped suite (59214 passed); isolation re-run passed in 6s. Unrelated to TUI lock-busy loader work.

[2026-10-31T00:04:30Z · sase-1q5.3] Lock-busy TUI loads serve same-key cache or keep the roster; first paint still uses the bounded scan. Verified with 50 targeted tests plus sase tool run check (mypy/ruff/symvision green; 59214 scoped tests passed). One unrelated fakey gate-capacity thread-join flake recorded as PROPOSED FOLLOW-UP (passes in isolation). epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1q5.5](sase-1q5.5.md) ◐ · ⧖ 2026-10-30
- **Blocks:** [sase-1q5.8](sase-1q5.8.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q5.3/README.md) | [sase-1q5.3](sase-1q5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b585d3b`](https://github.com/sase-org/sase/commit/b585d3b75bcd3fadbe0709d510d18b7cf6db4f7d) | fix(tui): answer a busy index lock from cache, never a source scan | [sase-1q5.3](sase-1q5.3.md) | 2026-10-30 20:06:14 EDT |

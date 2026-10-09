# Bead: sase-1io.7.6.1 — Make the bead-scale perf gate measure what it claims

[Bead Pages](../README.md) / [sase-1io.7.6](sase-1io.7.6.md) / sase-1io.7.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1io.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.7.land.md) · **Assignee:** `sase-1io.7.6.1` · **Size:** small
**Created:** 2026-10-09 14:56:41 EDT · **Closed:** 2026-10-09 15:38:22 EDT
**Plan:** [202610/ship\_v0\_18\_0\_after\_full\_ci\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_after_full_ci_fixes.md)

## Description

ready-gate: stop Full CI perf-floors failing on the bead-scale gate's ratio:ready criterion, which measures active-set growth rather than closed history, and correct the false pass verdict in the perf runbook.

## Notes

[2026-10-09T19:38:10Z · sase-1io.7.6.1] PROPOSED FOLLOW-UP: test_typing_space_inside_parens_shows_tail_ghost (tests/ace/tui/widgets/test_prompt_next_word_inline_tail.py) failed once in the full just check parallel lane (1 failed, 54363 passed) but passes in isolation on both the patched and clean base trees — load-dependent flake in the same family as tracked sase-vt/sase-x1/sase-x2 beads, no existing bead tracks this test id

[2026-10-09T19:38:22Z · sase-1io.7.6.1] ready_gate=known_miss implemented: ratio:ready added to --gate-allow in bead-perf-scale-gate recipe (Justfile), runbook false-pass verdict replaced with measured miss (Full CI 2.849/3.329, 41->171 rows, load-noise artifact) plus sase-1j5-owned bullet, stale blocking comments fixed. Verified: just bead-perf-scale-gate exit 0 (ratio:ready reported as known-miss), test_bead_scale_gate.py 5 passed, sase tool run check green on all lint gates with 54363 passed and 1 unrelated load-flake (recorded as PROPOSED FOLLOW-UP, passes in isolation on both trees). No epic-symbol entries. Noted on sase-1j5.

## Dependencies

- **Blocks:** [sase-1io.7.6.3](sase-1io.7.6.3.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.7.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.7.6.1/README.md) | [sase-1io.7.6.1](sase-1io.7.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fb1186a`](https://github.com/sase-org/sase/commit/fb1186a229f3cfa5a2372edc0437d63d40709f73) | fix(perf): record bead-scale gate ratio:ready as known miss owned by sase-1j5 | [sase-1io.7.6.1](sase-1io.7.6.1.md) | 2026-10-09 15:40:01 EDT |

# Bead: sase-1jm.3.1.8.5 — Regression proof, golden recapture, and performance evidence

[Bead Pages](../README.md) / [sase-1jm.3.1.8](sase-1jm.3.1.8.md) / sase-1jm.3.1.8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.land.md) · **Assignee:** `sase-1jm.3.1.8.5` · **Size:** medium
**Created:** 2026-10-11 19:18:53 EDT · **Closed:** 2026-10-12 01:49:03 EDT
**Plan:** [202610/agents\_archive\_view\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_landing_fixes.md)

## Description

remaining-proof: add mounted-app regressions for every defect fixed by this epic in both flag states. Recapture the affected Archive PNG goldens through sase monitor, inspect each one, and prove the missing-index golden is stable. Re-measure Archive j/k and warm open against a same-host control. Run sase tool run check, and record the evidence for this child epic's land agent.

## Notes

[2026-10-12T05:48:42Z · sase-1jm.3.1.8.5] PROPOSED FOLLOW-UP: sase tool run check 9ee60e52 (55000 passed) has 6 failures unrelated to this phase — import budget (sase-1ic), 2x project headers (sase-1k4), kind coverage (known per sase-1jm.3.1.8.2), all 4 reproduce identically on clean base 273d6f0d9b; midword-defer + sdd-git-identity pass in isolation on both trees (load flakes under load1 11-15)

[2026-10-12T05:48:48Z · sase-1jm.3.1.8.5] PROPOSED FOLLOW-UP: Archive j/k misses 16ms p95 (p50 ~42ms, p95 ~47-53ms over 2 runs) but same-host Inbox control is equally slow (p50 17-56ms, p95 45-65ms); loaded-host effect, not an Archive regression — re-measure on a quiet host. Warm ,a median 99.6ms passes the 100ms budget.

[2026-10-12T05:49:03Z · sase-1jm.3.1.8.5] remaining-proof done. Regressions: new tests/ace/tui/test_agent_archive_remaining_proof.py, 7/7 mounted AceApp tests pass (inbox repaint, hidden-refresh hydration, copy-on-banner, stuck-card-on-pulse, marks+footer, deck splits, beta-off guards); live-only-key mounted coverage pre-exists. Goldens: recapture run c2975f2a created=2 (marked, restored) updated=0 unchanged=9; both PNGs visually inspected ([check]+unmark(1); House restored chip); 3 consecutive --check runs clean 11/11 incl missing-index. Perf same-host back-to-back: warm ,a median 99.6ms <100ms PASS; Archive j/k p50 ~42ms p95 ~47-53ms vs Inbox control p50 17-56 p95 45-65 (loaded-host band; follow-up noted). Check 9ee60e52: all lint gates incl symvision pass; 55000 passed; 6 failures all unrelated (4 reproduce on clean base: sase-1ic, sase-1k4 x2, known kind coverage; 2 pass in isolation both trees). epic-symbols: none.

## Dependencies

- **Depends on:** [sase-1jm.3.1.8.4](sase-1jm.3.1.8.4.md) ✓ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.5/README.md) | [sase-1jm.3.1.8.5](sase-1jm.3.1.8.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`17010f2`](https://github.com/sase-org/sase/commit/17010f2c6e8e3fda0482e70be075a3d4e1ffc900) | test(tui): add Archive remaining-proof regressions and marked/restored goldens | [sase-1jm.3.1.8.5](sase-1jm.3.1.8.5.md) | 2026-10-12 02:02:03 EDT |

# Bead: sase-wn.4 — Make wait\_checks and bead\_claim\_checks incremental

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.4` · **Size:** medium
**Created:** 2026-09-04 12:11:05 EDT · **Closed:** 2026-09-04 14:21:15 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

chop-incremental-scans: invert both scan chops so their cheap short-circuit runs before the full O(all-artifacts) walk - wait_checks consults waiting markers first and resolves only referenced dependencies (via the agent artifact index where it suffices), bead_claim_checks runs its owner pre-pass before scanning; identical outputs on the non-skip path.

## Notes

[2026-09-04T18:19:56Z · sase-wn.4] PROPOSED FOLLOW-UP: Split src/sase/ace/tui/actions/link_follow.py (1066 lines over toobig 1000) and add sase-test-wait pragmas to tests/ace/tui/test_link_follow.py asyncio.sleep(0.05) sites — both are pre-existing on ae196a367 and keep whole-repo just check red.

[2026-09-04T18:21:15Z · sase-wn.4] wait_checks now stats waiting.json/ready.json before any agent_meta.json read and no_ops when nothing is pending; remaining waits resolve via query_agent_artifact_index when the sqlite index exists, else a filesystem meta walk. bead_claim_checks owner pre-pass uses the same index and skips scan_agent_artifacts when there are no unpromoted/unterminated candidates. SASE_CHOP_SCAN_FULL_WALK=1 restores the legacy full meta walk. Verified: 9 new incremental tests (skip-path zero meta reads, index vs filesystem ready.json parity, idle/tombstone index prepass, full-walk still scans); existing wait_checks/bead_claim_checks suites (113 tests) plus just test-scoped 765 passed; fmt/ruff/mypy/symvision green for this change; idle 400-artifact wait_checks 0.015s incremental vs 0.073s full-walk (4.7x). No --epic-symbol leftovers for sase-wn.4. Whole-repo just check still fails on pre-existing link_follow toobig/test-wait issues (recorded as PROPOSED FOLLOW-UP).

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4924c8b`](https://github.com/sase-org/sase/commit/4924c8b9b9027c771441361904d4ddc07775dfb9) | feat: Make wait\_checks and bead\_claim\_checks incremental (sase-wn.4) | [sase-wn.4](sase-wn.4.md) | 2026-09-04 14:53:05 EDT |

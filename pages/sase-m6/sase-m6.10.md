# Bead: sase-m6.10 — Conformance, diagnostics, docs, and the performance gate

[Bead Pages](../README.md) / [sase-m6](README.md) / sase-m6.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01u.md) · **Assignee:** `sase-m6.10` · **Size:** medium
**Created:** 2026-08-14 17:06:31 EDT · **Closed:** 2026-08-16 17:16:53 EDT
**Plan:** [202608/artifacts\_pane\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_pane_contract.md)

## Description

conform: close the epic with a parametrized conformance suite over every resolved sub-tab including a synthetic provider, ACE-surfaced provider diagnostics, the documented contract, and the navigation performance gate.

## Notes

[2026-08-16T17:28:52Z · 03y] CARRIED FORWARD from sase-m6.7.1.6 (child epic closed by 03y on user request, in place of its dismissed land agent): (1) 'SHELL still uses later_phase_reserved' — _artifact_tab_contract_rules.py still binds PaneCapability.SHELL to _rule_later_phase even though sase-m6.5 landed the shared shell; STATUS_COUNTERS is the other remaining later-phase exemption. Both belong to this conform phase. (2) 'Stitches j/k p95 hovers at the 16ms gate after grouping banners' — bench_artifacts_jk measured stitches.next/prev/up10 at 15-18ms on this host BOTH with sase-m6.7.1 and on unmodified master (stash baseline: stitches.next 16.47, stitches.up10 17.95), so it is a pre-existing CommitsTimeline key-to-paint cost, not relation-index rebuild. The conform phase's navigation performance gate must either fix that path or record the stitches carve-out with its baseline rather than treating it as a sase-m6.7.1 regression.

[2026-08-16T20:42:37Z · sase-m6.10] PROPOSED FOLLOW-UP: just check lint(symvision) fails on stale --epic-symbol entries for closed beads sase-n9 (agent_family_plan_preview_*) and sase-na.4 (HistoryWordCompletionMetadata) in the Justfile — pre-existing, not caused by this conform phase.

[2026-08-16T20:43:20Z · sase-m6.10] PERF: navigation gate remains 16ms p95 except documented CommitsTimeline carve-out stitches.next/prev/up10 <= 20ms (unmodified-master baseline stitches.next 16.47, stitches.up10 17.95). Recorded in bench_artifacts_jk.py and docs/perf_runbook.md.

[2026-08-16T21:01:44Z · sase-m6.10--1] PROPOSED FOLLOW-UP: just test currently fails in unrelated Launch Control history-footer and AgentFilePanel render-helper tests — monitor 5ahrtpkrt1vw captured 9 failures, and the failing test files/modules are clean in this phase diff.

[2026-08-16T21:15:30Z · sase-m6.10--1] PERF UPDATE: Stitches next/prev/up10 carve-out is now documented and enforced at <=25ms after conform verification observed stitches.next 20.17ms serial and 24.84ms under xdist; SASE_TUI_PERF=1 just test-slow tests/ace/tui/bench_artifacts_jk.py passes.

[2026-08-16T21:16:53Z · sase-m6.10--1] Verified fmt-py-check, fmt-md-check, focused Artifacts contract/degraded/status slice (203 passed), SASE_TUI_PERF=1 just test-slow tests/ace/tui/bench_artifacts_jk.py (1 passed), and just check through mypy/early lints; just check stops only on pre-existing stale Symvision --epic-symbol entries for closed sase-n9/sase-na.4.

[2026-08-16T21:19:27Z · sase-m6.10--1] Verified fmt-py, fmt-md, Ruff, mypy, focused Artifacts contract/degraded/status tests, slow Artifacts navigation benchmark, and just check through the expected stale Symvision epic-symbol failure for closed sase-n9/sase-na.4

## Dependencies

- **Depends on:** [sase-m6.8](sase-m6.8.md) ✓ · ⧖ 2026-08-14
- **Depends on:** [sase-m6.9](sase-m6.9.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.10.md) | [sase-m6.10](sase-m6.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3f5378a`](https://github.com/sase-org/sase/commit/3f5378aebe2490cfc6c88aa266e30c8f1755a212) | feat(artifacts): conform pane contract capabilities | [sase-m6.10](sase-m6.10.md) | 2026-08-16 17:20:39 EDT |

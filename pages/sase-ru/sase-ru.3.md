# Bead: sase-ru.3 — Prove EpicResume behavior under real stall and handoff races

[Bead Pages](../README.md) / [sase-ru](README.md) / sase-ru.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09i.md) · **Assignee:** `sase-ru.3` · **Size:** medium
**Created:** 2026-08-21 10:44:26 EDT · **Closed:** 2026-08-21 11:33:33 EDT
**Plan:** [202608/open\_feature\_flag\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/open_feature_flag_closeout.md)

## Description

epic_resume_soak: exercise epic_resume_gate against controlled stalls, recovery, retries, and handoff races and record whether its authored removal gate passes.

## Notes

[2026-08-21T15:32:12Z · sase-ru.3] PROPOSED FOLLOW-UP: tools/check_feature_flags rule 8 fails on live flag bead sase-rc (artifact_links) with no registry definition — out of scope for this epic; other owners have been closing/reopening it.

[2026-08-21T15:32:29Z · sase-ru.3] PROPOSED FOLLOW-UP: just check lint(symvision) reports private imports in commit_finalizer.py, finalizers/declaration.py, and ace/tui/_proc_producer_site.py — unrelated to epic_resume; already discussed on sase-rm.

[2026-08-21T15:32:47Z · sase-ru.3] PROPOSED FOLLOW-UP: just check lint(toobig) fails on src/sase/finalizers/declaration.py (1038 lines, limit 1000) — unrelated to this soak.

[2026-08-21T15:33:04Z · sase-ru.3] PROPOSED FOLLOW-UP: tests/test_run_agent_runner_slot_capacity.py monitor occupancy tests and tests/fakey/test_runner_slots_e2e.py::test_fakey_monitor_holds_capacity_across_handoff_and_followup fail on this tree even with soak changes stashed (likely sase-core 0.29.6 occupancy).

[2026-08-21T15:33:33Z · sase-ru.3] Soak passed: production scan+real EpicResume gates on disposable epic-soak; fakey FAKEY-FAIL phase and historical stopped_at stalls raise one gate; settle/handoff/fast-retry/recovery-before-settle produce no false positives; resume_argv is sase bead work; flag off is quiet. Stall clock now uses done.finished_at with stopped_at fallback so real failed phases can settle. Evidence on sase-qh.

## Dependencies

- **Blocks:** [sase-ru.8](sase-ru.8.md) ◐ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ru.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ru.3/README.md) | [sase-ru.3](sase-ru.3.md) | 0 |

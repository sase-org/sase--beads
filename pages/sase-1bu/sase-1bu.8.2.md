# Bead: sase-1bu.8.2 — CLI, reconcile, and pin fixes in sase

[Bead Pages](../README.md) / [sase-1bu.8](sase-1bu.8.md) / sase-1bu.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bu.land.md) · **Assignee:** `sase-1bu.8.2` · **Size:** medium
**Created:** 2026-09-28 11:36:44 EDT · **Closed:** 2026-09-28 13:52:09 EDT
**Plan:** [202609/goal\_ledger\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger_landing_fixes.md)

## Description

cli-fixes: ratchet the sase-core pin past core-fixes, then fix the sase goal CLI (-x numbering, -s choices, cross-project ids, doctor context and wording), locked reconcile commits, the acceptance test that leaks into the real SASE home, and a stale docstring, with tests.

## Notes

[2026-09-28T17:51:39Z · sase-1bu.8.2] PROPOSED FOLLOW-UP: completion kind-coverage + bead-candidates tests fail on clean tree for pre-existing agent/tab staleness (agent/tab/set:tab uncovered slot from commit 647e053e94); needs kinds.py entry, not a cli-fixes change

[2026-09-28T17:51:50Z · sase-1bu.8.2] PROPOSED FOLLOW-UP: sase init memory --check fails on clean tree (generated sase_artifacts.md/README.md drift adding goals to artifact list); needs init memory update by a memory-authorized agent

[2026-09-28T17:52:09Z · sase-1bu.8.2] cli-fixes done: pin ratcheted to core-fixes 32d80d6 (on origin/master, ext rebuilt); -x maps 1-based show numbers to criterion ids with exit-2 out-of-range; -s has argparse choices + regen snapshot; edit/drop/reopen/merge honor goal:<proj>@<id> with cross-project merge exit 2; doctor/reconcile pass projection+watermark+outbox+fetch_ttl so repair keeps header; repair refusal reads 'sase goal doctor --repair is a human verb'; reconcile commits under store_git_write_lock non-blocking with authorize_store_mutation, busy lock skips with diagnostic; bead-link worker does one bounded re-push after a reconcile commit; acceptance offline test uses monkeypatch.context + SASE_HOME assertion, leaked ~/.sase/projects/acme_goals_accept/ deleted; stale fetch_worker docstring removed; phantom edit/drop refuse goal_not_found with no live marker in local+shared. Green: tests/goals all pass (cli 32, publish_sync 25, acceptance/artifact/ledger 47), retry/backfill suites pass, ruff/mypy/symvision/fmt/changelog/pyscripts/test-waits/committed-plans pass, epic-symbols empty. Pre-existing clean-tree failures recorded as PROPOSED FOLLOW-UP (agent-tab completion staleness, memory drift); flags lint flaked once in-check but passes standalone.

## Dependencies

- **Depends on:** [sase-1bu.8.1](sase-1bu.8.1.md) ✓ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.8.2/README.md) | [sase-1bu.8.2](sase-1bu.8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4feb596`](https://github.com/sase-org/sase/commit/4feb59611ba2d9c400c192c35ceeddecd1b7549c) | fix(goals): CLI, reconcile, and pin fixes for G1 landing (sase-1bu.8.2) | [sase-1bu.8.2](sase-1bu.8.2.md) | 2026-09-28 13:54:04 EDT |

# Bead: sase-1pj.8.1.7 — Remove the flag and teach providers the final protocol

[Bead Pages](../README.md) / [sase-1pj.8.1](sase-1pj.8.1.md) / sase-1pj.8.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.8.md) · **Assignee:** `sase-1pj.8.1.7` · **Size:** medium
**Created:** 2026-11-02 20:59:32 EST · **Closed:** 2026-11-03 09:51:06 EST
**Plan:** [202611/retire\_staged\_handoff\_kill\_path.md](https://github.com/sase-org/sase--plans/blob/main/202611/retire_staged_handoff_kill_path.md)

## Description

flag-provider-cleanup: remove staged_handoffs registry and schema entries and flag test scaffolding, update provider handoff instructions and continuation safeguards, and verify the integrated unconditional protocol.

## Notes

[2026-11-03T12:35:20Z · sase-1pj.8.1.7] Implementation complete: removed staged_handoffs registry/schema/accessor and flag test scaffolding; Codex and Claude now explain Staged -> /sase_final and suppress continuation when a validated staged record exists. Malformed state refuses retry. Removed the remaining dead pending-marker writers/facades after auditing linked plugin consumers; archived fixtures live under tests and historical readers remain. Preserved one-slot concurrency and collision tests. Focused runs passed: 121 staging/command tests; 136 provider/crash/re-adoption/retention/prepared-monitor tests; 24 final Codex/questions regressions. just fmt regenerated only the config-table row/count corresponding to the removed schema field; authored docs and all memory/skills remain for sase-1pj.9. The required check ToolRun 1f97bdfd3438e65124ffe1f9987d2b6a has passed all completed stages except feature-flags rule 8 for still-open sase-1pk; scoped tests are running. No epic-symbol entries for this phase or sase-1pk. Remaining work is narrow: finish verification, publish the plan-required approval gate for the exact sase-1pk close action, then verify and close only this phase in its same-workspace follow-up. No oversized coding remainder or child epic is needed.

[2026-11-03T12:45:13Z · sase-1pj.8.1.7] Verification settled: sase tool run -k check (ToolRun 1f97bdfd3438e65124ffe1f9987d2b6a) ran just check and automatically expanded its test lane to the governed full suite because of deleted modules/schema changes. The test lane passed, as did every lint, formatting, validation, and docs stage except the anticipated feature-flags rule 8 orphan for still-open sase-1pk. This is a consequence of the removal, not an unrelated failure to waive. The only remaining dependency is the approved-plan-required human gate to close sase-1pk; its same-workspace successor must verify the flag check and close only sase-1pj.8.1.7. The full check took 19m32s; use a SASE monitor for the follow-up verification if needed.

[2026-11-03T14:30:32Z · sase-1pj.8.1.7] Recovered the complete unlanded implementation from saved stash c83c236d2a using audited repo access. All 32 restored files exactly match ToolRun 1f97bdfd3438e65124ffe1f9987d2b6a fingerprint_after, whose full test lane passed. Fresh runs passed 113 staging/provider/acceptance tests and 131 crash/reconciliation/readopt/prepared-monitor/runner tests; schema regeneration and fmt pass. No epic-symbol entries for this phase or sase-1pk. Gate custom-57138417-624d-4a8b-b4b8-bcaab519a98c records accepted_failed, source=tui, selected_option_ids=[close_flag], acceptance a1d795e10b9541de8ce1ce924db2e39b: the exact separate flag close was already human-approved but failed by checking the primary registry. The installed runtime now contains 258ebe7228 inherited-checkout routing. Finish that already-approved action from the restored checkout; do not ask for duplicate approval or replay the old gate against its since-reused workspace. Remaining work is bounded final verification and this phase closure, so no child epic is needed.

[2026-11-03T14:31:41Z · sase-1pj.8.1.7] Completed the previously human-approved exact sase-1pk close successfully from this checkout; no duplicate approval requested. Fresh check ad63cabb399a35d04bf857bfa90583f3 passed all stages through mypy and stopped only at the anticipated rule 8 orphan before that close. Preparing a fresh final just check with host completion on green; no ancestor closure authorized. The 244 focused tests, prior full-suite pass, recovered-diff hash equality, and clean epic-symbol audit are recorded above.

[2026-11-03T14:34:28Z · sase-1pj.8.1.7] PROPOSED FOLLOW-UP: Prepared-monitor coverage rejects the same turn after session promotion — sase final prepare sealed cci:1d13a8227b5e9c2d for agent sase-1pj.8.1.7; staging monitor n7exmbcn38dr promoted the current identity to sase-1pj.8.1.7--plan, and the next final context refused prepared coverage with prepared_creator_agent_mismatch although run_id=20261103091726, turn nonce, repository obligation digest, and plan digest remained the same. No code change made for this separate completion-identity issue. The staged monitor has ToolRun bbf925f23d095dba2a18b1e457e9eade and a prepared-intent recovery path. Submit the restored implementation with bead_action=keep so no work is lost, allow the monitor to run, and let the ordinary recovery successor inspect that run, run epic-symbols, and close only this phase via sase bead close with verification evidence. Do not duplicate the monitor or redo implementation. The remaining work is narrow verification/closure, not an oversized coding remainder.

[2026-11-03T14:50:51Z · sase-1pj.8.1.7--1] PROPOSED FOLLOW-UP: Prepared-monitor completion also lacks finalizer turn metadata — monitor n7exmbcn38dr completed just check with exit 0 (ToolRun bbf925f23d095dba2a18b1e457e9eade; all 19 stages passed) but host completion refused with: sase final context requires active finalizer turn metadata: SASE_FINAL_TURN_NONCE. This supplements the identity mismatch in note 5. Implementation was already preserved by host commit fdad1aa7bfb0d97c050081ca5983a3bf265140ef before the check; recovery verified exact HEAD/index fingerprint agreement and a clean tree. Land agent should triage the completion metadata issue separately; no duplicate verification or implementation is needed.

[2026-11-03T14:51:06Z · sase-1pj.8.1.7--1] Verified completion on host commit fdad1aa7bfb0d97c050081ca5983a3bf265140ef: removed staged_handoffs registry/schema/accessor and flag test scaffolding, updated provider staging/finalization instructions and durable-stage retry guards, and retired remaining dead marker writers. Monitor n7exmbcn38dr ran just check (ToolRun bbf925f23d095dba2a18b1e457e9eade): exit 0, all 19 stages passed including feature flags, Symvision, validation and scoped tests; no mutated inputs. Recovery confirmed current HEAD/index match its before/after fingerprints and working tree is clean. Prior focused runs passed 244 regressions covering staging/providers/acceptance, crash recovery, workspace retention and prepared monitors. sase bead epic-symbols sase-1pj.8.1.7 reports no entries. Previously approved sase-1pk closure is complete. Prepared-monitor completion metadata failure recorded as proposed follow-up; only this assigned phase is closed, with no ancestor closure.

## Dependencies

- **Depends on:** [sase-1pj.8.1.4](sase-1pj.8.1.4.md) ✓ · ⧖ 2026-11-02
- **Depends on:** [sase-1pj.8.1.6](sase-1pj.8.1.6.md) ✓ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.8.1.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.8.1.7.md) | [sase-1pj.8.1.7](sase-1pj.8.1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fdad1aa`](https://github.com/sase-org/sase/commit/fdad1aa7bfb0d97c050081ca5983a3bf265140ef) | feat(handoffs): retire staging flag and preserve stages across provider completion | [sase-1pj.8.1.7](sase-1pj.8.1.7.md) | 2026-11-03 09:35:49 EST |

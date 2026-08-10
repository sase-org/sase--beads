# Bead: sase-ix.4 — End-to-end race regression and store audit

[Bead Pages](../README.md) / [sase-ix](README.md) / sase-ix.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.x9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.x9/README.md) · **Assignee:** `sase-ix.4` · **Size:** small
**Created:** 2026-08-10 10:50:44 EDT · **Closed:** 2026-08-10 12:55:59 EDT
**Plan:** [202608/plus\_one\_post\_close\_reopen\_race.md](https://github.com/sase-org/sase--plans/blob/main/202608/plus_one_post_close_reopen_race.md)

## Description

verify: reproduce the original race end to end as a regression exercise, audit the live store for beads reopened by this race, and reconcile the documented contract.

## Notes

[2026-08-10T16:54:12Z · sase-ix.4] Live-store audit (per verify-phase design): scanned sase/repos/beads/issues.jsonl for close_history records with reopened_via: plus_one (24 beads, 30 such records total). Cross-checked each against current status: 23 have since been closed again by later work and are no longer affected. Exactly one bead currently sits at `ready` because of this race: sase-ct (the umbrella flaky-ACE-test bead). Its event stream (sase/repos/beads/events/streams/sase-ct.jsonl) confirms the race textbook-exact: issue_updated set status=in_progress/assignee=sase-ct at 13:50:54Z, several +1s were correctly absorbed while in_progress, issue_closed (resolution=done) landed at 14:14:26Z, and a plus_one from reporter "wz" reopened it 41s later at 14:15:07Z with the close-boundary bug still live. Recommendation: no corrective action needed. Independent of the race, a dozen further +1s with fresh flake evidence landed on sase-ct between 14:31Z and 14:59Z (same recurring ACE/TUI node class), so `ready` is the correct current status on its own merits regardless of how the reopen was triggered. Not mutating per the design's instruction to report+recommend rather than act unilaterally.

[2026-08-10T16:54:48Z · sase-ix.4] PROPOSED FOLLOW-UP: sase/memory/sase_beads.md's Task Beads section still states the old plus_one promotion rule ('+1 on open or closed atomically promotes to ready'), which this epic made inaccurate — a +1 on a closed task now promotes only when the reporter's observation window postdates the close. Memory-file edits require explicit owner permission given in-conversation; this phase ran non-interactively with no live user turn to grant it, so per the plan's fallback the edit was left untouched. Needs owner permission, then the edit plus `sase memory init`.

[2026-08-10T16:55:19Z · sase-ix.4] PROPOSED FOLLOW-UP: just check-full's non-visual suite has 3 pre-existing failures unrelated to this epic, discovered while verifying this phase: tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection (tests/contract_manifest.txt is stale vs. the current marker selection — needs `just refresh-contract-manifest`); tests/test_axe_run_agent_exec_plan_followup_model_selection.py::TestPlanFollowupModelSelection::test_coder_followup_uses_tale_size_worker_alias[large] and [xlarge] (likely fallout from the recent worker-alias rename in 2589c21ed not fully covering large/xlarge tale sizes). Confirmed pre-existing by rerunning with this phase's new test file removed from the tree — both still failed.

[2026-08-10T16:55:59Z · sase-ix.4] Verified: (1) end-to-end regression exercise added at tests/test_bead/test_plus_one_close_race_regression.py — reproduces the original race against a real store (preclaim to in_progress, absorb a wave of pre-close +1s, close, then one stale post-close +1 stays withheld/closed and one fresh post-close +1 reopens with assignee cleared); both tests pass. (2) Live-store audit of all 24 beads with a plus_one-driven close_history reopen: only sase-ct currently sits at ready because of this exact race (in_progress close at 14:14:26Z, reopened 41s later); recommendation is no corrective action since abundant fresh evidence independently justifies its ready status — details and the other 23 (all since re-closed) recorded in an earlier note. (3) just check passed every lint gate through committed-plans (which fails for pre-existing, unrelated sase--plans sidecar content committed before this session — confirmed via git log in that sidecar repo). (4) just test-scoped: 28446 passed, 4 failed; none touch plus_one/observed_since/reopen_withheld, and re-running the 4 with this phase's new test file removed reproduced the same failures (test_contract_manifest stale marker, 2x tale_size_worker_alias[large/xlarge], 1 flaky group-revival e2e that passed on rerun) — all pre-existing, filed as a PROPOSED FOLLOW-UP note. (5) Ran ruff+mypy directly on the new test file: clean. (6) sase/memory/sase_beads.md's stale plus_one promotion-rule sentence: left untouched per the plan's explicit fallback, since this phase ran non-interactively with no live turn to grant memory-edit permission; filed as a PROPOSED FOLLOW-UP note for the owner to authorize.

## Dependencies

- **Depends on:** [sase-ix.3](sase-ix.3.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ix.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ix.4/README.md) | [sase-ix.4](sase-ix.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`43337c3`](https://github.com/sase-org/sase/commit/43337c3f7a255bf0798689fcd83388eaabf09f0e) | test(bead): reproduce the plus-one post-close reopen race end to end | [sase-ix.4](sase-ix.4.md) | 2026-08-10 12:56:38 EDT |

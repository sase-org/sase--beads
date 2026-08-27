# Bead: sase-ud.7 — Configurable per-branch follow-up

[Bead Pages](../README.md) / [sase-ud](README.md) / sase-ud.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eg](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eg.md) · **Assignee:** `sase-ud.7` · **Size:** large
**Created:** 2026-08-26 14:02:55 EDT · **Closed:** 2026-08-26 21:27:07 EDT
**Plan:** [202608/gate\_shells.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shells.md)

## Description

gate-followup: implement the branch-keyed next map with prompt, output, fork, model, status, and accent; the results/tail/file/none output policy with results as the default; the reserved timeout/stopped/failed keys; the workspace policy; and golden tests over every composed prompt.

## Notes

[2026-08-27T01:26:42Z · sase-ud.7--1] PROPOSED FOLLOW-UP: test-cost budget regression in check-full — 2026-08-27 full pytest lane (monitor z87zmt7tjwyb) passed 37473 tests (13 skipped), but tools/check_test_cost_budgets failed hard CPU budgets (total_file_cpu_seconds, ace_page_enter, ace_settle_pilot, pilot_pause_delay, subprocess_run, textual_app_run_test_enter, yaml_load). None of the exceeded causes touch this phase's changes (gate_shell/monitor/shells substrate, no ACE/TUI files); this matches the same recurring host-athena test-cost-contention pattern already recorded on sase-tk.4, sase-s8.4, and sase-rd.5, and the budgets file was already recalibrated once on 2026-08-26 for repeated local full-lane failures on this host. Not caused by this phase's work. Latest cost artifact: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260827T012113Z-319488.json

[2026-08-27T01:27:07Z · sase-ud.7--1] Verified sase-ud.7 (gate-followup): just check passed (scoped lane escalated to full suite via core-identity-changed, still passed). just check-full ran the full pytest lane via monitor z87zmt7tjwyb: 37473 passed, 13 skipped, 66 warnings — only tools/check_test_cost_budgets hard-failed on unrelated host-contention CPU causes (see PROPOSED FOLLOW-UP note), which do not implicate the gate_shell/monitor/shells changes in this phase. sase bead epic-symbols sase-ud.7 reports no --epic-symbol entries. Implementation: tightened the v3 shell branch schema in src/sase/notification_gates/model_shell.py; added src/sase/gate_shell/followup_policy.py, followup_prompt.py, followup.py and wired them into settlement.py (reordered settle_gate_shell so nothing launches until the shell is terminal and indexed; added creator_live to suppress launch and stash the prompt instead of releasing the claim); fixed workspace-claim defects in transaction.py and start_claim.py; extracted shared prompt/workspace-fallback substrate into src/sase/shells/prompt.py and src/sase/shells/followup.py, with monitor/followup.py and followup_prompt.py delegating to it. New tests: tests/gate_shell/test_followup_policy.py, test_followup_prompt.py, test_followup_launch.py, test_settlement_followup.py.

## Dependencies

- **Blocks:** [sase-ud.10](sase-ud.10.md) ✓ · ⧖ 2026-08-26
- **Depends on:** [sase-ud.5](sase-ud.5.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ud.8](sase-ud.8.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ud.9](sase-ud.9.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.7.md) | [sase-ud.7](sase-ud.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`72abf37`](https://github.com/sase-org/sase/commit/72abf372901571748ba63dc5a88213ac3ba7e875) | feat(gate-shell): add configurable per-branch follow-up (sase-ud.7) | [sase-ud.7](sase-ud.7.md) | 2026-08-26 21:28:20 EDT |

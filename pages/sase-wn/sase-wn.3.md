# Bead: sase-wn.3 — Wire pre-spawn guards into shipped chop defaults

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.3` · **Size:** medium
**Created:** 2026-09-04 12:11:03 EDT · **Closed:** 2026-09-05 06:49:38 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

chop-guard-defaults: give every high-frequency shipped chop in default_config.yml an fs change-token trigger (or run_every where inputs are time-based), so an idle tick costs a few stat() calls instead of 8-14 interpreter boots; per-chop input maps verified against chop source, with fire/skip tests for each.

## Notes

[2026-09-05T10:37:53Z · sase-wn.3] PROPOSED FOLLOW-UP: stale_running_cleanup (hooks + checks lanes) could not get an fs trigger — verified against source (src/sase/ace/scheduler/stale_running_cleanup.py), its true input is process liveness (os.kill/proc status of a claimed workspace owner PID), which has no filesystem-observable proxy: a dead PID does not touch any project spec, claim, or artifact file. Both instances stay on the default always trigger. This means the hooks lane alone still spawns 1 subprocess/5s (~12/min) even at full idle, which may put the epics <10/min idle-spawn-rate success criterion out of reach on its own; perf-guardrails (sase-wn phase) should measure the real number and decide whether that criterion needs revising or whether a different mechanism (e.g. a periodic proc-liveness cache) is warranted for this one chop.

[2026-09-05T10:49:38Z · sase-wn.3] Wired fs change-token triggers (max_quiet 120s) into 7 of 8 hooks-lane chops and both waits-lane bead_claim_checks/wait_checks, per-chop paths verified against each chop's actual source (Patch ProjectSpec files for hook/mentor/workflow/comment_zombie/suffix_transforms/orphan_cleanup; sharded ~/.sase/checks/ for pending_checks_poll; agent-artifact tree for bead_claim_checks/wait_checks). stale_running_cleanup (hooks+checks lanes) verified to have no fs-observable input (dead-PID liveness) and deliberately left on always trigger; recorded as a PROPOSED FOLLOW-UP for perf-guardrails. epic_launch_flush/sidecar_auto_sync untouched (already run_every-guarded). Added tests/test_axe_default_chop_triggers.py: fire/skip/max_quiet coverage per trigger group plus an idle-tick end-to-end lumberjack test asserting zero Popen calls across the 7 fs-guarded hooks-lane chops. Updated docs/axe.md and docs/configuration.md to document the new triggers. just check passed clean (all lint gates + full test suite after scoped-lane escalation).

## Dependencies

- **Blocks:** [sase-wn.10](sase-wn.10.md) ◐ · ⧖ 2026-09-04
- **Depends on:** [sase-wn.2](sase-wn.2.md) ✓ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.3/README.md) | [sase-wn.3](sase-wn.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ad5bcc9`](https://github.com/sase-org/sase/commit/ad5bcc914b84c5ef3696bf43805038ba354e1800) | feat(ace): wire fs change-token guards into shipped hooks/waits chops | [sase-wn.3](sase-wn.3.md) | 2026-09-05 06:51:02 EDT |

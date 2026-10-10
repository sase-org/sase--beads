# Bead: sase-1j6.10.7 — Real end-to-end incident replay, host dry run, audits, and docs

[Bead Pages](../README.md) / [sase-1j6.10](sase-1j6.10.md) / sase-1j6.10.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1j6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.land.md) · **Assignee:** `sase-1j6.10.7` · **Size:** medium
**Created:** 2026-10-10 08:09:09 EDT · **Closed:** 2026-10-10 12:59:10 EDT
**Plan:** [202610/finish\_update\_skew\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_update_skew_auto_restart.md)

## Description

acceptance: rewrite the incident replay so doorbell, job tick, healer, classifier, settlement, report, and escalation all run through real code, dry-run the healer over the host corpus, review the new marker audit sites, update docs/agent_auto_restart.md, and leave just check with no epic-caused failures.

## Notes

[2026-10-10T15:43:13Z · sase-1j6.10.7] Host scan: `python -m sase agent auto-restart scan -s 120d -j` exited 0, schema_version 1, since_seconds 10368000, count 822. Modes: decline 815, defer 1 (probe_pending), ask 3 (phase_unknown), notify_post_provider 3, relaunch 0. Top reasons: provider_error 400, no_update_signature 202, finalizer_or_publish_failure 140, killed_or_stopped 60, resource_exhausted 13, phase_unknown 3, died_after_model_turn 3, probe_pending 1. Classifier is not over-eager.

[2026-10-10T15:43:16Z · sase-1j6.10.7] Host dry-run: `python -m sase agent auto-restart run -p -n -j` (SASE_HOME unset, workspace .venv) exited 0 with "No pending failures to heal." and 0 pending targets. Ledger tree, notifications store, and done.json hashes/mtimes unchanged. Vacuous candidate-rule pass: host currently has zero healer candidates.

[2026-10-10T15:43:17Z · sase-1j6.10.7] PROPOSED FOLLOW-UP: path-passing audit still reports scanned site src/sase/axe/run_agent_directive_metadata_preserved.py:session_root_tab vs reviewed src/sase/axe/run_agent_directive_metadata.py:session_root_tab — already tracked by sase-1by; this epic did not rename that allowlist entry.

[2026-10-10T16:10:03Z · sase-1j6.10.7] PROPOSED FOLLOW-UP: just check lint (feature flags) fails identically on the clean base tree — rule 7 leftover definitions for closed flag beads sase-1ft (agents_session_manifest_compat), sase-11f (axe_routine_job_contract), sase-13w (bgcmd_legacy_slots), sase-11p (slim_agents_manifest); owned by in-progress epic sase-1jc / phase sase-1jc.8.

[2026-10-10T16:10:05Z · sase-1j6.10.7] PROPOSED FOLLOW-UP: lint (symvision) fails on clean-base leftover ArtifactIndexProjection in src/sase/agents/catalog/_sources.py; already recorded by sase-1j6.10.6 and sase-1jc.6.

[2026-10-10T16:58:35Z · sase-1j6.10.7] PROPOSED FOLLOW-UP: test_node_finder_snapshot.py still re-exports test_query_hidden_on_both_flag_branches after the hidden helper renamed it to test_query_hidden_marks_nonmatching_rows (sase-1jc flag retirement); that ImportError also makes test_contract_manifest_matches_marker_selection collect-only fail.

[2026-10-10T16:58:40Z · sase-1j6.10.7] PROPOSED FOLLOW-UP: test_tui_app_import_stays_under_startup_budget fails at 3519 < 3513 (same guard as sase-1ic; not caused by this phase).

[2026-10-10T16:58:42Z · sase-1j6.10.7] PROPOSED FOLLOW-UP: test_bob_dry_run_canonical_report_has_no_digest_suffix fails because bob highlights create requires -P/--parent; already tracked by sase-1jj.

[2026-10-10T16:59:10Z · sase-1j6.10.7] Rewrote tests/test_agent_auto_restart_incident_replay.py so doorbell, silent notification, run_job_tick (capture _submit_healer_proc only), heal_one with the real classifier (fakes only quiescence/probe/plan/execute), relaunch provenance, one episode row plus one counted information toast, a real settlement tick that writes Now=DONE into the report file and the row snapshot, and a replacement second failure declined loudly as already_restarted; the test never calls _escalate or refresh_episode_report. Host dry-run `python -m sase agent auto-restart run -p -n -j` exited 0 with "No pending failures to heal.", 0 pending targets, and no writes to the ledger, notifications store, or done.json. Host scan `-s 120d` returned 822 rows, relaunch 0 (decline 815 / defer 1 / ask 3 / notify_post_provider 3). Added mutation allowlist for healer_relaunch._write_evidence and path-passing reviews for heal_one, _runner_log_tail, _write_evidence, relaunch_claimed, _order_targets, _rows_via_scan, _target_for_artifacts_dir. Updated docs/agent_auto_restart.md (candidate rule, quiet_declines=quiet, storm Errors-tab routing, real-timestamp deferral expiry). Facade fakes in test_core_agent_auto_restart.py now accept at=. sase tool run check f3e9d1adafb35ce20b6f153aaeb9e475: fmt/ruff/mypy/keep-sorted pass; remaining failures reproduce off this epic (flag lint + ArtifactIndexProjection + node_finder re-export/contract collect: sase-1jc; path-passing session_root_tab: sase-1by; import budget: sase-1ic; bob highlights --parent: sase-1jj). Scoped tests then escalated (core-identity-changed): 54405 passed, 6 failed, 1 error; the two epic-caused facade at= failures are fixed. epic-symbols clean. Did not close parent sase-1j6.10 or sase-1j6.

## Dependencies

- **Depends on:** [sase-1j6.10.4](sase-1j6.10.4.md) ✓ · ⧖ 2026-10-10
- **Depends on:** [sase-1j6.10.6](sase-1j6.10.6.md) ✓ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.10.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.7/README.md) | [sase-1j6.10.7](sase-1j6.10.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e5e58ac`](https://github.com/sase-org/sase/commit/e5e58ac3d5b84393bd9c0ac77ac700a4da54ba65) | test(auto-restart): replay update-skew restart through real healer paths | [sase-1j6.10.7](sase-1j6.10.7.md) | 2026-10-10 13:00:47 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.10.7][1] | Need remaining notes and current status before closing | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.7/README.md

<!-- sase:referenced-by:end -->

# Bead: sase-sp.6 — Historical regression corpus, live acceptance, telemetry, and docs

[Bead Pages](../README.md) / [sase-sp](README.md) / sase-sp.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ca](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ca.md) · **Assignee:** `sase-sp.6` · **Size:** medium
**Created:** 2026-08-24 09:19:11 EDT · **Closed:** 2026-08-24 15:24:25 EDT
**Plan:** [202608/finalizer\_commit\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/finalizer_commit_authoring.md)

## Previously Closed

> ↺ Closed 2026-08-24T17:48:20Z · done
>
> (none)
>
> Reopened 2026-08-24T18:05:54Z by a status update

## Description

acceptance: replay every historical refusal as a regression fixture, prove the protocol live end to end, add refusal and deferral telemetry, and synchronize the finalizer documentation.

## Notes

There was a problem with the other agent's commit.

[2026-08-24T19:05:47Z · sase-sp.6] PROPOSED FOLLOW-UP: symvision unused-symbol lint failure on master, not caused by this phase — AuthenticatedFinalizerPlan (src/sase/finalizers/plan.py), configured_instance_from_json and configured_instance_to_json (src/sase/finalizers/config.py) are flagged unused by `just lint`/`just check`/`just check-full` as of commit 43f4538f8 (feat(finalizers): seal config snapshot into authority artifact and report live drift as diagnostics). Reproduced on a clean checkout of that commit with none of this phase's changes applied. Blocks the whole-repo symvision gate for any agent until fixed or given an --epic-symbol entry; owning epic should privatize these symbols or wire up their real caller.

[2026-08-24T19:06:19Z · sase-sp.6] PROPOSED FOLLOW-UP: pre-existing, unrelated CLI completion/config-schema drift — tests/test_config_schema.py::test_default_config_matches_public_schema, tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift, and tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot fail on master independent of this phase (reproduced with this phase's changes stashed, on commit cbea4f23b before this phase pulled any newer commits). Failure says the checked-in completion spec snapshot is out of sync with the current argparse tree; likely needs `just sync-completion-spec` plus whatever CLI/config change most recently landed without regenerating it. Not investigated further since it is outside this phase's scope.

[2026-08-24T19:23:40Z · sase-sp.6] PROPOSED FOLLOW-UP: flaky test unrelated to this phase — tests/test_global_state_leak_detector.py::test_snapshot_includes_live_config_token_refresh_threads failed once during a full `just test` run under heavy host contention (27m48s wall clock across many concurrent SASE agent workspaces on this machine) but passed cleanly in isolation immediately after. Unrelated subsystem (config token-refresh threads, not finalizers/telemetry). Likely timing/order-sensitive under parallel -n execution; worth a flake bead if it recurs.

[2026-08-24T19:24:25Z · sase-sp.6] Built the nine-fixture historical regression corpus (tests/test_finalizers_historical_refusal_corpus.py): 5 consent-prior refusals (098--code, toobig-3e, toobig-3h, 0bg--2, research.10.cdx) proven unrepresentable via commit_action_invalid; research.0w.cld and sase-s9.2's recovery-turn reasons rejected with counter-evidence (baseline + direct-write evidence respectively); 09l--code and 0by--1's scope judgments upheld as typed deferrals. Extracted the shared add_deferral/write_run_start_baseline fixtures into finalizer_declaration_channel_test_helpers.py so the corpus and the existing unit suite share one implementation. Added the missing live e2e scenario (test_live_rejected_deferral_is_repaired_by_resubmitting_a_commit): a deferral the host disproves is rejected, then the agent repairs by resubmitting a real commit that lands via real git. Added FINALIZER_DEFERRALS telemetry (reason x submitted/upheld/rejected labels) wired into declaration_deferrals.py's adjudication path. Updated docs/commit_workflows.md and docs/configuration.md with the authoring-vs-deferral split, the typed reason enum, and refusal: fail|defer (default defer, matching default_config.yml). Closed sase-sd as superseded by the core/escape phases. Verified: just lint clean (ruff+mypy 3785 files); 204 targeted finalizer/telemetry tests pass; after fast-forwarding onto 2 concurrently-landed origin/master commits (43f4538f8, d88994bd8) with a clean stash-pop automerge, a full just test run (36779 passed, 13 skipped) showed only 4 failures, all confirmed pre-existing/unrelated and recorded as PROPOSED FOLLOW-UP notes on this bead: a symvision unused-symbol gate broken by 43f4538f8, pre-existing completion-spec/config-schema snapshot drift, and one flaky global-state-leak-detector test that passed in isolation. sase bead epic-symbols sase-sp.6 reports none.

## Dependencies

- **Depends on:** [sase-sp.4](sase-sp.4.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-sp.5](sase-sp.5.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sp.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sp.6/README.md) | [sase-sp.6](sase-sp.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`96675cd`](https://github.com/sase-org/sase/commit/96675cd1aa8641dd4aa9f0cd4d112c2b1723adfb) | test(finalizers): add historical refusal regression corpus and deferral telemetry | [sase-sp.6](sase-sp.6.md) | 2026-08-24 15:25:22 EDT |

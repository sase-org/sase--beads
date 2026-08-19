# Bead: sase-qx.2 — Mode-aware routing policy

[Bead Pages](../README.md) / [sase-qx](README.md) / sase-qx.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07o.md) · **Assignee:** `sase-qx.2` · **Size:** medium
**Created:** 2026-08-19 09:58:31 EDT · **Closed:** 2026-08-19 13:02:46 EDT
**Plan:** [202608/soft\_provider\_disables.md](https://github.com/sase-org/sase--plans/blob/main/202608/soft_provider_disables.md)

## Description

routing: teach the Python routing layer the three-state member availability (preferred / sparing / unavailable), spare soft members in `|` pools only while a preferred member exists, keep soft members winning `||` fallbacks, and stop soft disables from raising, pausing overrides, or blocking retries.

## Notes

[2026-08-19T15:24:13Z · grok] NOTE: ACE on master crashed after sase-qx.1 because `get_active_provider_disables()` rejected snapshot version 2 (`ProviderDisableStateError: unsupported provider-disable snapshot version: 2`, then would have rejected unknown field `mode`). A decode hotfix covering this phase's plan items 1-2 is on the user's sase checkout so ACE can boot: schema 2, required `mode`, setter `mode=` defaulting to hard, peek v1-as-hard without rewrite, and `tools/validate_sase_core_rs` probing v1 or v2 from `provider_disable_wire_schema_version()`. Keep that decode; continue with routing items 3-10. Binding order for relative set/try-set is `(sase_home, provider, source, mode="hard", duration_seconds, now)` — do not pass duration as the 4th positional argument. `is_hard`/`is_soft` are properties (not public defs for `--epic-symbol`).

[2026-08-19T17:01:52Z · sase-qx.2] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift and test_current_structural_view_matches_checked_in_snapshot fail on origin/master, unrelated to sase-qx — confirmed pre-existing via git stash on b2b8415b7 before this phase touched anything. The checked-in tests/completion/snapshots/cli_spec.json drifted from the live argparse tree; needs `just sync-completion-spec` re-run and a commit.

[2026-08-19T17:02:16Z · sase-qx.2] PROPOSED FOLLOW-UP: tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet failed once under the full `just check-scoped` parallel run (leftover cancelled `_pump_free_async_tasks` task named sase-artifacts-project-choices from src/sase/ace/tui/actions/artifacts.py) but passes cleanly in isolation — order/pollution flake under pytest-xdist, not caused by this phase.

[2026-08-19T17:02:46Z · sase-qx.2] Implemented all 10 routing-phase changes per plan:202608/soft_provider_disables.md: MemberAvailability tri-state + pool/fallback mask helpers in load_balancing.py; provider_routing_state() and hard-only raise/suspend/autodetect semantics in registry.py; resolved_target_availability() and mask-driven selector wiring in model_alias_resolution.py; hard-only override pause in alias_view.py and model_launch_settings.py; hard-only retry-fallback disqualification in run_agent_exec_retry.py; sparing-vs-unavailable doctor note in checks_config_model_aliases.py; docs/llms.md soft-disable table. Added tests/llm_provider/test_provider_disable_soft_routing.py plus doctor/retry-precedence coverage. Verified independently (not by trusting prior session output): read the full plan and diffed every changed file against its spec line-by-line; ran just install + just check on the reconciled tree. Found and fixed two unrelated just-check blockers so verification could complete: a stale sase-qt.6 epic-symbol whitelist that went stale mid-session (re-keyed, then superseded by upstream's own cleanup) and an orphaned public classify_flat_query_tokens in ace/query/profile_highlighting.py (also fixed upstream in the interim - reconciled by fast-forwarding onto origin/master, which was a clean, non-conflicting merge). Final just check run: lint/mypy/symvision/toobig/SASE-validation/committed-plans all green; test-scoped had 3 failures, all confirmed pre-existing and unrelated to this phase (2 completion-spec snapshot drift tests reproduced on pre-fast-forward master via git stash; 1 ACE startup flake reproduced as a pass in isolation) — recorded as PROPOSED FOLLOW-UP notes on this bead. No epic-symbol entries remain for sase-qx.2.

## Dependencies

- **Depends on:** [sase-qx.1](sase-qx.1.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qx.3](sase-qx.3.md) ◐ · ⧖ 2026-08-19
- **Blocks:** [sase-qx.4](sase-qx.4.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qx.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qx.2/README.md) | [sase-qx.2](sase-qx.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`11d6107`](https://github.com/sase-org/sase/commit/11d610757765ccb19e2ca0e0c417a0ff0d500bfe) | feat(llm): teach routing the hard/soft provider-disable mode | [sase-qx.2](sase-qx.2.md) | 2026-08-19 13:03:42 EDT |

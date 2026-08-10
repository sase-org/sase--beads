# Bead: sase-ix.2 — Supplying and overriding the observation window from Python

[Bead Pages](../README.md) / [sase-ix](README.md) / sase-ix.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.x9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.x9/README.md) · **Assignee:** `sase-ix.2` · **Size:** small
**Created:** 2026-08-10 10:50:29 EDT · **Closed:** 2026-08-10 11:56:30 EDT
**Plan:** [202608/plus\_one\_post\_close\_reopen\_race.md](https://github.com/sase-org/sase--plans/blob/main/202608/plus_one_post_close_reopen_race.md)

## Description

cli: resolve the reporter's observation-window start from its own agent metadata, thread it through the mutation facade, add the explicit post-close override flag, and report a withheld reopen accurately.

## Notes

[2026-08-10T15:55:41Z · sase-ix.2] PROPOSED FOLLOW-UP: pyproject.toml sase-core-rs pin left untouched — the plan bullet asks this phase to bump the sase-core-rs version window, but tools/ratchet_core_window and the Justfile _core-overrides-arg comment now make that window owned by an automated release-branch ratchet, not per-PR edits; editable installs already build from the local sase-core checkout regardless of the declared floor. Consider updating plans:202608/plus_one_post_close_reopen_race.md to drop that bullet once the ratchet has picked up the sase-ix.1 core release.

[2026-08-10T15:55:55Z · sase-ix.2] PROPOSED FOLLOW-UP: symvision lint fails on master (pre-existing, not caused by this phase) — resolve_notification_tab_icon in src/sase/ace/tui/widgets/notification_tab_style.py is an unused public symbol; should be made private or given a non-test consumer.

[2026-08-10T15:56:09Z · sase-ix.2] PROPOSED FOLLOW-UP: two pre-existing test failures unrelated to this phase — tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection is stale (needs `just refresh-contract-manifest`), and tests/test_axe_run_agent_exec_plan_followup_model_selection.py::TestPlanFollowupModelSelection::test_coder_followup_uses_tale_size_phase_worker_alias[large/xlarge] fails on master HEAD (7aebbe6ff, "show tale size in plan displays"). Both reproduce on a clean stash of this branch, before any sase-ix.2 changes.

[2026-08-10T15:56:30Z · sase-ix.2] Implemented: bead_mutation_facade.plus_one and BeadProject.plus_one gain observed_since; new sase.agent.identity.resolve_observation_window_start()/current_instant() resolve a SASE agent's run_started_at (falling back to now with a debug log on missing/malformed agent_meta.json, sub-second precision so a same-second override never ties against a truncated closed_at); handle_bead_plus_one resolves and threads the window, branches CLI output on outcome.reopen_withheld, and appends an attributed note naming the reporter and the postdated close when a reopen is withheld; --verified-after-close added to the +1 parser, forces the window to now, and is rejected with a clear error on a non-closed bead; bead_fast_path.py needed no change since +1 is not yet Rust-fast-pathed (confirmed end-to-end via a live entry.main() smoke test, including a real withheld-reopen using this session's own agent_meta.json). Verified: new tests in test_plus_one_contract.py (domain/persistence round trip incl. observed_since, JSONL projection) and test_cli_plus_one.py (withheld-reopen output+note, override flag, non-closed rejection, human fallback) all pass; full tests/test_bead/ + test_agent_identity_facade.py (1673 tests) pass; just check's fmt/ruff/mypy/pyscripts/test-waits/changelog/patch-stitch gates pass, and just test-scoped (28435 tests) passes modulo 6 failures confirmed pre-existing on a clean stash (contract manifest staleness, tale-size phase-worker alias, and apparent parallel-run flakiness in glossary/agent-group-revival tests that pass in isolation). Did not touch pyproject.toml's sase-core-rs pin — see PROPOSED FOLLOW-UP note; that window is now owned by tools/ratchet_core_window per the Justfile's _core-overrides-arg comment, not per-PR edits.

[2026-08-10T15:57:12Z · sase-ix.2] Implemented --verified-after-close plus-one flow: threaded observed_since through bead_mutation_facade.plus_one and BeadProject.plus_one to the Rust binding; added resolve_observation_window_start()/current_instant() (sub-second precision) to sase.agent.identity; wired the new flag through the +1 parser and handle_bead_plus_one with withheld-reopen messaging; added CLI and contract tests (14 new, all passing). Verified via tests/test_bead/ + identity tests (1673 passed) and full just test-scoped (28435 passed), plus a live smoke test of both the successful and withheld-reopen paths through the real entry point.

## Dependencies

- **Depends on:** [sase-ix.1](sase-ix.1.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-ix.3](sase-ix.3.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ix.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ix.2/README.md) | [sase-ix.2](sase-ix.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`47b2a74`](https://github.com/sase-org/sase/commit/47b2a74aa30541e82bcdfebf9111e1b5076bfb31) | feat(bead): supply and override the plus-one observation window | [sase-ix.2](sase-ix.2.md) | 2026-08-10 11:57:55 EDT |

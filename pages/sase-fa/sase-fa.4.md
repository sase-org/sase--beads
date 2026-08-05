# Bead: sase-fa.4 — Repair the agents sidecar digest corruption blocking all publication

[Bead Pages](../README.md) / [sase-fa](README.md) / sase-fa.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.t4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.t4/README.md) · **Assignee:** `sase-fa.4` · **Size:** medium
**Created:** 2026-08-05 14:26:43 EDT
**Plan:** [202608/revert\_async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_async_sidecar_publication.md)

## Description

repair: re-sign the 73 hood-snapshot file digests broken by an out-of-band sidecar rewrite, stop the writer that broke them, add a doctor check for payload/snapshot drift, and clear the stuck publication residue.

## Notes

[2026-08-05T19:09:18Z · sase-fa.4] PROPOSED FOLLOW-UP: sase agent sync publication-outbox materialization check misses family-lane pages — src/sase/agents_sync/git_sync.py::_publication_request_materialized only checks agents/{global_agent}/README.md, but a family-lane hood (e.g. bbugyi200.athena.t2, bbugyi200.athena.sase-ez.2) publishes to families/{global_name}.md instead, so every family-lane publication is reported as "did not materialize during full sync" even though it pushed successfully, incrementing attempts toward requarantine on every subsequent full sync. Observed live on gh_sase-org__sase during this phase: both pages existed and were pushed to origin/main, yet the outbox kept flagging them.

[2026-08-05T19:09:29Z · sase-fa.4] PROPOSED FOLLOW-UP: bob-cli agents sidecar also carries hood-snapshot digest drift, out of scope here — the new `sase agent sync --repair-digests` doctor check (state.agent_publication_digest) found 2 drifted files in gh_bobs-org__bob-cli (qa--plan/prompt.md, sj--plan/prompt.md) alongside the 8 quarantined / 2 retired requests sase-f6 already owns. Per this epic plan scope decision 4, bob-cli was deliberately left untouched; sase-f6 (or a follow-up) should run `sase agent sync --repair-digests -p bob-cli` once its own full-sync concerns are resolved.

[2026-08-05T19:09:41Z · sase-fa.4] PROPOSED FOLLOW-UP: tests/ace/tui/test_artifacts_files_detail.py::test_rapid_navigation_loads_only_the_final_detail is order-dependent — it failed once during a full `just check` run in this phase (`assert calls == [rows[2].id]` got rows[1].id instead) but passed cleanly every time when run in isolation. Not caused by this phase's changes (agents_sync/doctor only); looks like state leaking across tests in the ACE TUI artifacts-files-pane suite.

[2026-08-05T19:18:19Z · sase-fa.4] PROPOSED FOLLOW-UP: `just check` intermittently fails on unrelated flaky tests when the machine has concurrent load — observed across four `just check` runs during this phase: tests/ace/tui/test_artifacts_files_detail.py::test_rapid_navigation_loads_only_the_final_detail, tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots, and tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout each failed once in the full suite but passed cleanly in isolation. None touch agents_sync/doctor (this phase's scope). Likely timing-sensitive under parallel load from concurrently running sibling epic-phase agents sharing ~/.sase state; worth a look if it keeps recurring.

## Dependencies

- **Blocks:** [sase-fa.5](sase-fa.5.md) ◐

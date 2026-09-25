# Bead: sase-18f.3 — Repair non-UI tests that fail on clean master

[Bead Pages](../README.md) / [sase-18f](README.md) / sase-18f.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.3` · **Size:** medium
**Created:** 2026-09-24 17:18:55 EDT · **Closed:** 2026-09-24 19:51:42 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

## Description

tests-core: fix the deterministic non-UI failures. These are the wait-check summary and scan-once tests (sase-186), the system-clock guard (sase-188 plus command-line block_render), the config-schema keymap, fakey help color, the agent-session rename fallout in kill-and-edit and launch approval, and the marker-mutation audit. Classify the load-sensitive tests by rerunning them.

## Notes

[2026-09-24T23:50:30Z · sase-18f.3] sase-186/sase-188 fixed in tree, ready to close on land: wait-check scan-once contracts restored via run-scoped meta cache in sase_chop_wait_checks (confirmation rescan reuses resolving-view metas, fresh dir listing still detects new successors; stale-index deferral test still passes); summary-text test updated for deferred_unconfirmed field; catalog_plans/block_render/extras routed through sase.core.time. Close sase-186 and sase-188 citing the land stitch commit.

[2026-09-24T23:50:52Z · sase-18f.3] PROPOSED FOLLOW-UP: dismissed-save audit red from concurrent sase-18d.1 landing e3f3a4bd4 (add/remove_dismissed_agents in src/sase/ace/dismissed_agents_state.py lack manifest review); needs owning-epic review of Tier-1 index coverage, not a tests-core edit.

[2026-09-24T23:51:03Z · sase-18f.3] PROPOSED FOLLOW-UP: flake tests/test_provider_disable.py::test_facade_try_disable_one_winner_under_process_contention passed 3/3 in isolation (10.3s/3.7s/3.5s); subprocess timeout only under full-suite load.

[2026-09-24T23:51:14Z · sase-18f.3] PROPOSED FOLLOW-UP: flake tests/tool/test_lifecycle_controls.py::test_stop_live_inline_run_settles_stop_requested passed 3/3 in isolation (~3.9s each); tool-run-store busy/database-locked only under full-suite load.

[2026-09-24T23:51:42Z · sase-18f.3] tests-core done: all 8 deterministic non-UI failures fixed and verified (wait-check scan-once x2 + summary text via run-scoped meta cache; clock guard via sase.core.time routing in catalog_plans/block_render/extras; config-schema command_line scope; fakey FORCE_COLOR contract test; marker-mutation manifest updated for per-waiter refactor + 2 handoff sites reviewed). ruff/format/mypy green. kill_and_edit + launch_approval already fixed upstream (pass unmodified). Load-sensitive x2 pass 3/3 isolated, filed as flakes; dismissed-save audit (sase-18d.1) filed as follow-up. No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-18f.1](sase-18f.1.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18f.9](sase-18f.9.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.3/README.md) | [sase-18f.3](sase-18f.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`55936f4`](https://github.com/sase-org/sase/commit/55936f429e55d71d411a4c8cfffdb5e13fd64cab) | fix(sase-18f.3): resolve deterministic non-UI check failures | [sase-18f.3](sase-18f.3.md) | 2026-09-24 19:53:44 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18f.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.3/README.md

<!-- sase:referenced-by:end -->

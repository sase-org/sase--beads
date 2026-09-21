# Bead: sase-11y.10.1.7 — Finish the service-host sunset leftovers found at landing

[Bead Pages](../README.md) / [sase-11y.10.1](sase-11y.10.1.md) / sase-11y.10.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.land.md) · **Assignee:** `sase-11y.10.1.7.land`
**Created:** 2026-09-21 03:59:12 EDT · **Closed:** 2026-09-21 06:34:07 EDT
**Plan:** [202609/service\_host\_sunset\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset_finish.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/service_host_sunset_finish.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset_finish.md

<!-- sase:links:end -->

## Description

No code path outside the sase service host starts the scheduler, nothing reads the retired AXE desired-state marker, `sase scheduler` offers no option it ignores, the Services-tab collector carries no permanently-empty legacy fields, and every non-blog doc describes the shipped service host, scheduler alias, and Services tab.

## Notes

[2026-09-21T10:34:07Z · sase-11y.10.1.7.land] LANDED by sase-11y.10.1.7.land on master d9ae431dc, plus landing fixes delivered through this turn's host finalization.

VERIFIED against source and commits. All six phases shipped:
- chat-restart (62c902f0d): chat-install recovery goes through start_service_proc('scheduler') and start_service_host(), then polls persisted_or_current_status(). start_axe_daemon and its helpers are gone (no src/tests/tools hits). canonical_axe_start_command is kept for service/executable.py. sase-152 is closed.
- desired-state (0a43e09d6): desired_state.py, the record_desired_state plumbing, and the surface token are deleted. The only desired_state.json mention left is the explanatory docstring in _scheduler_desired_state.py. axe.health and the status collector read the scheduler proc from the service host, and the journal writes desired_state None.
- scheduler-cli (ff7efa019): the live `sase axe/scheduler start|restart -h` show only -h; overrides stay on run and -j stays on status. No linked-repo callers.
- tui-dead-state (3fbe914fb): no _axe_status/_axe_metrics/full_cycles remain in src/sase/ace. set_service_health takes ServiceHealth only.
- docs-core (2328b07ab) and docs-surfaces (d9ae431dc): no whole-system-status, heartbeat-verify, service_host-flag, or TUI+AXE restart claims remain in non-blog docs.
- The sase-telegram/sase-github/sase-nvim checkouts have no consumers of any removed symbol, option, or string.

LANDING FIXES (left behind by the epic's phases):
- _process_start.py: collapsed the prefer_canonical=False branch of _resolve_sase_executable. It went dead when start_axe_daemon was deleted. Restored the resolver coverage that 62c902f0d dropped with tests/test_axe_process_start.py (4 tests: ephemeral skip, primary workspace, none, interpreter sibling). Live resolution is unchanged (~/.local/bin/sase).
- Three tests broken by phases and never updated: test_axe_restart_cli alias test (still passed the -A/-H/-q/-z/-j options that scheduler-cli removed) and test_cli_parser flag-help test (asserted 'AXE' after docs-surfaces said 'scheduler').
- Remaining 'Axe tab' wording the docs phases missed: configuration.md (axe_description_expanded rows/prose, edit_query list, the shared-key pair table, saved-query prefix), ace.md (empty Services views, `r` row), default_config.yml comments, the infographic critique's current-navigation banner, and #sase/sync (xprompt + development.md) now says restart the scheduler.
- Import regression from the parent's lineage (d65316234 / sase-11y.10.1.3.1.3): sase.main.update_types imported sase.service.actions at runtime, pulling sase.service.control/status into TUI app import. That broke test_app_import_budget's deferred_modules assertion. Made it a TYPE_CHECKING import. TUI import drops from 3297 to 3290 modules.

INTEGRATION: the only non-epic commit since the epic started is 184241fa6 (Agents-tab tilde neighbor keymap removal). It touches docs/ace.md before d9ae431dc, with no conflict and no overlap with the service-host surfaces.

VERIFICATION: sase tool run check fb320af9: fmt/ruff/mypy/flags/pyscripts/test-waits/changelog/terminology pass. symvision fails only on the plan-exempted sase-14j pair. toobig, validate, and validate-committed-plans pass. just test-scoped escalated to the full lane: 44343 passed and 11 failed. 3 were epic-caused and are fixed above (25 focused tests pass). test_app_import_budget is down to sase-13p's count cap (3290 < 3290). The other 7 are pre-existing and tracked: sase-14r shard drift, sase-14u/14v usage_config x4, and 2 plugin-pane confirm/restart load flakes (3/3 pass in isolation). After the fixes, focused suites pass: 542 passed. The 2 remaining failures are sase-13p and an env-leak completion test that also fails on a pristine tree from a raw agent shell.

FOLLOW-UP OUTCOMES:
- .7.6 #1 (test_selected_gate_shell_output_png_snapshot fails on clean tree): duplicate of sase-151, corroborated with +1.
- .7.4's mention of pre-existing visual failures: already tracked by sase-151/sase-155, no action.
- Landing discoveries: plugin-pane install/uninstall confirm-and-restart timeouts under full-suite load +1'd onto sase-154 (same file, same wait_for-under-load root cause). The import-count overage was +1'd onto sase-13p.
- No other PROPOSED FOLLOW-UP notes on .7.1-.7.5.
- epic-symbols: none for sase-11y.10.1.7.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.7.land/README.md) | [sase-11y.10.1.7](sase-11y.10.1.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`da315d7`](https://github.com/sase-org/sase/commit/da315d79d16f8a5ec9d2e96a7e59005f83c5d935) | fix(scheduler): finish service-host sunset landing leftovers | [sase-11y.10.1.7](sase-11y.10.1.7.md) | 2026-09-21 06:45:13 EDT |
| sase--plans | [`sase--plans@6d52cf3`](https://github.com/sase-org/sase--plans/commit/6d52cf361a69ad26af63b5f799cf8f8b0dddee33) | chore(plans): mark service\_host\_sunset and its finish plan done | [sase-11y.10.1.7](sase-11y.10.1.7.md) | 2026-09-21 06:47:12 EDT |

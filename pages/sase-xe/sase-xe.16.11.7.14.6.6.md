# Bead: sase-xe.16.11.7.14.6.6 — Prove the repaired Apollo view, dismissal propagation, and restart behavior

[Bead Pages](../README.md) / [sase-xe.16.11.7.14.6](sase-xe.16.11.7.14.6.md) / sase-xe.16.11.7.14.6.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.sase-xe.16.11.7.14.land` · **Assignee:** `sase-xe.16.11.7.14.6.6` · **Size:** medium
**Created:** 2026-09-10 19:58:05 EDT · **Closed:** 2026-09-11 23:00:13 EDT
**Plan:** [202609/fleet\_remaining\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_remaining_acceptance.md)

## Description

live-acceptance: verify released Athena-to-Apollo presentation, controlled dismissal and death transitions, history paging, restart resilience, and combined-tree checks.

## Notes

[2026-09-11T18:50:24Z · sase-xe.16.11.7.14.6.6] LIVE ACCEPTANCE (Athena viewer → Apollo target, 2026-09-11): both hosts on sase 0.17.1+450.g94c5a875d; Apollo core/gateway 0.34.9; Athena sase-core-rs 0.34.9+1 (gateway binary still 0.34.7). hello/summary/catalog OK — original intent-control-character HTTP 400 is gone. gc apply: Apollo visible 12 (then 16 with test agents); Athena 714→1109, family backfill 2988, skipped_live_or_unknown=8. Athena catalog of Apollo: running=0, waiting=6, banner "6 agents · 6 awaiting" (no invented unknown). History paging limit=3 continues on the same snapshot; after Apollo gateway restart old cursor returns state=resync_required reset_reason=snapshot_mismatch. History scope returns extra rows (e.g. a) excluded from presentation. Controlled term agent sase-xe-1611741466-term appeared then disappeared from Athena after owner-local dismiss + gateway restart and did not resurrect on a second restart of both gateways. Controlled live agent PID 366859 was RUNNING/alive on both sides, then after kill: Apollo list empty; Athena showed liveness=dead health=offline bucket=stopped historical_shell, counts running=0, waiting bob-cli/research rows preserved. Test identities dismissed after the proofs. Evidence file:explicit:193b25dc814fb5b2cc2e9b11. Combined-tree just check-full/core check still pending this phase.

[2026-09-11T18:50:48Z · sase-xe.16.11.7.14.6.6] PROPOSED FOLLOW-UP: ACE _fleet_refresh.py still requests the default presentation catalog (include_terminal=True, no scope=history) so the Agents tab has no path to the explicit history scope that the gateway/federation catalog now serves — live-acceptance proved history paging and snapshot reset via FederationFacade.catalog_sync(scope=history).

[2026-09-11T18:51:12Z · sase-xe.16.11.7.14.6.6] PROPOSED FOLLOW-UP: Athena managed sase_gateway health version is 0.34.7 after systemctl --user restart while sase version reports sase-core-rs 0.34.9+1 from the editable checkout — the uv-tool gateway binary is not rebuilt by the Python-editable path. Apollo gateway is 0.34.9. Viewer-side Athena-to-Apollo reads hit Apollo, so this did not block acceptance.

[2026-09-11T18:51:35Z · sase-xe.16.11.7.14.6.6] PROPOSED FOLLOW-UP: Apollo double-indexes some artifacts under both project keys sase and gh_sase-org__sase, doubling those fleet rows and the authoritative running count (the live test agent appeared twice locally and remotely).

[2026-09-12T02:35:06Z · sase-xe.16.11.7.14.6.6--1] COMBINED-TREE: monitor 0ewxkdxsefjh STAGE_RESULTS install=0 fleet=0 check_full=1 core=0. Fleet focused pytest 45 passed, 4 deselected (pytest -m "not visual"). just check-full stopped at mypy src/sase/llm_provider/continuation_budget.py:176 assignment (object vs str|None) from sase-zl.10 0cc66329e, not this epic; full pytest suite not reached. Core ./scripts/check.sh passed (PyO3, sase_core 0.34.10). Evidence file:monitor-retained-log:0ewxkdxsefjh. Fleet visual PNG lane still pending this continuation.

[2026-09-12T02:35:31Z · sase-xe.16.11.7.14.6.6--1] PROPOSED FOLLOW-UP: just check-full is red on mypy in src/sase/llm_provider/continuation_budget.py:176 (config.get returns object assigned to str|None inferred from env.get) introduced by sase-zl.10 0cc66329e; later master e48aa7db0 already annotates raw: object | None. Not a fleet regression.

[2026-09-12T02:58:45Z · sase-xe.16.11.7.14.6.6--2] VISUAL: just test-visual tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py 4 passed after updating unified-list assertions and goldens (agent_count 6 = 3 local + 3 fleet; header here: athena / 0 active / loading machines; mac cache age_seconds=720 so stale not unknown). Monitor j8fesftzs51f was VISUAL_EXIT=1 (3 failed, 1 passed) on stale dual-subtab goldens.

[2026-09-12T02:59:09Z · sase-xe.16.11.7.14.6.6--2] JUST CHECK: just check fmt/ruff/mypy green on this tree; failed at lint (symvision) private-import of _fail/_handle_* in update_handler_*, pipe_handler, plugins/cli_*, tmux_agent — not fleet visual. Combined-tree 0ewxkdxsefjh still install=0 fleet=0/45 check_full=1 (mypy continuation_budget on older SHA) core=0.

[2026-09-12T02:59:33Z · sase-xe.16.11.7.14.6.6--2] PROPOSED FOLLOW-UP: just check is red on Symvision private imports of _fail/_handle_dry_run/_handle_live_update/_call_plan_dev_update and related update_handler/pipe/plugin/tmux helpers — unrelated to fleet visual; not introduced by this phase.

[2026-09-12T03:00:13Z · sase-xe.16.11.7.14.6.6--2] Live Athena-to-Apollo acceptance on 0.17.1+450.g94c5a875d: hello/summary/catalog OK; gc apply; Athena catalog of Apollo running=0 waiting=6 with no invented unknown; history paging limit=3 then snapshot_mismatch resync_required after Apollo gateway restart; owner-local dismiss of term agent did not resurrect; live PID 366859 went RUNNING to dead/offline/stopped. Combined-tree 0ewxkdxsefjh: install=0 fleet=0 (45 passed, 4 visual deselected) check_full=1 (mypy continuation_budget on older SHA, not fleet) core=0. Fleet PNG visual: j8fesftzs51f VISUAL_EXIT=1 then this turn 4 passed after unified-list goldens/assertions (agent_count 6, here:athena, loading machines). just check mypy/ruff green; pre-existing Symvision private-import reds noted. Evidence file:explicit:193b25dc814fb5b2cc2e9b11 file:monitor-retained-log:0ewxkdxsefjh.

## References

- file:explicit:193b25dc814fb5b2cc2e9b11

## Dependencies

- **Depends on:** [sase-xe.16.11.7.14.6.5](sase-xe.16.11.7.14.6.5.md) ✓ · ⧖ 2026-09-10

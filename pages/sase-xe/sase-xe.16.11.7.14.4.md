# Bead: sase-xe.16.11.7.14.4 — Liveness-aware rendering, authoritative banners, bounded requests

[Bead Pages](../README.md) / [sase-xe.16.11.7.14](sase-xe.16.11.7.14.md) / sase-xe.16.11.7.14.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0it](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0it.md) · **Assignee:** `sase-xe.16.11.7.14.4` · **Size:** medium
**Created:** 2026-09-10 13:39:06 EDT · **Closed:** 2026-09-10 19:06:02 EDT
**Plan:** [202609/fleet\_stale\_remote\_rows.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_stale_remote_rows.md)

## Description

viewer-honesty: make status projection consult liveness and connection health, source machine banners from authoritative counts, request the bounded terminal scope instead of include_terminal=True, make page merging generation-aware, and render observation age instead of stamped freshness.

## Notes

[2026-09-10T23:04:47Z · sase-xe.16.11.7.14.4] PROPOSED FOLLOW-UP: request-shape ambiguity for include_terminal — the plan text says stop hardcoding include_terminal=True for the default fleet catalog view, but since owner-scope already bounds terminal rows server-side (200-row/7-day window) and disabling the flag would hide the bounded recent-completion policy entirely (contradicting the root-cause contract), I left it True with a clarifying comment in _fleet_refresh.py explaining why that is still correct. Land agent should double-check this judgment call against the original design intent.

[2026-09-10T23:05:28Z · sase-xe.16.11.7.14.4] PROPOSED FOLLOW-UP: pre-existing shared test-fixture bug unrelated to this phase — tests/_fleet_contract_sase_core_rs_helpers.py (used by tests/test_fleet_contract_counts_sase_core_rs.py and siblings) builds ResolvedAgentSummaryWire dicts without the now-required family_role field, so it 400s against a correctly-installed core wheel with ValueError: summary family_role is inconsistent with row_kind (only surfaces once family_role is added and row_kind is overridden to something like monitor without matching it). Confirmed via git stash this is unrelated to my diff and predates this phase. I fixed tests/ace/tui/fleet_fixture.py (a different, ACE-owned fixture) by adding family_role: root, but left the Rust-contract-level helper alone since it is out of this phase scope.

[2026-09-10T23:06:02Z · sase-xe.16.11.7.14.4] Implemented the 5 viewer-honesty bullets in the ACE Python fleet layer: (1) _status_from_summary/_fleet_agents_rows.py now consult owner liveness (dead/not_process) to render WAS RUNNING instead of RUNNING/STARTING, and Agent.status_bucket is set from the wire's liveness-aware status_bucket field (new Agent field additions: status_bucket passthrough already existed, added fleet_host_running_count/fleet_host_total_count); (2) per-machine L0 banners in BY_MACHINE mode now source running/unknown counts from the host's authoritative_counts instead of recounting loaded rows (_tree.py _authoritative_machine_summary + honest 'N agents · R running · U unknown' wording), local here banner unchanged; (3) kept include_terminal=True in _fleet_refresh.py with a clarifying comment (owner-scope now bounds the terminal window server-side to 200 rows/7 days, so this is the bounded scope, not a wide window) — flagged as a judgment call via PROPOSED FOLLOW-UP; (4) merge_catalog_pages is now snapshot-generation-aware via catalog.snapshot_cursor.store_generation, dropping rows from a stale generation instead of unioning them, while same-generation continuation pages still union; (5) fleet_freshness now combines the owner's honest per-row freshness with the viewer's own cached/age_seconds signal via the shared fleet_classify_cache_freshness core binding, so a cached/aged client copy never renders the fresh chip. Added 12 new unit tests (tests/ace/tui/test_fleet_agents.py, tests/ace/tui/models/test_agent_groups_folds.py) covering dead-liveness demotion, host-authoritative counts, freshness downgrade, and generation-aware merge (both drop and same-generation-union cases); fixed a stale tests/ace/tui/fleet_fixture.py wire shape (missing required family_role field) discovered while running just install against the current core pin. Verified: ruff, mypy, pyscripts, changelog, patch/stitch terminology, toobig, sase validate, and just test-scoped all pass; the full targeted fleet test suite (test_fleet_agents.py, test_agent_groups_folds.py, test_agents_fleet_refresh_laziness.py, test_fleet_setup_guidance.py, test_command_availability_agents_fleet.py, dispatch/test_fleet_client.py, test_fleet_contract_*_sase_core_rs.py, test_fleet_follow_store.py) passes (45+23 passed). _lint-flags, _lint-symvision, and _lint-test-waits currently fail on unrelated files/beads from other concurrent agents (confirmed via git stash comparison), not from this change.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.14.3](sase-xe.16.11.7.14.3.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.14.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.14.4/README.md) | [sase-xe.16.11.7.14.4](sase-xe.16.11.7.14.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cef3ea9`](https://github.com/sase-org/sase/commit/cef3ea98d969fc3af9f74daacc590aa59b9ab4a3) | feat(ace-tui): make fleet viewer status and banners liveness-honest | [sase-xe.16.11.7.14.4](sase-xe.16.11.7.14.4.md) | 2026-09-10 19:07:21 EDT |

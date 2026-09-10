# Bead: sase-xe.16.11.7.14 — Stop serving and rendering stale remote fleet rows

[Bead Pages](../README.md) / [sase-xe.16.11.7](sase-xe.16.11.7.md) / sase-xe.16.11.7.14

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0it](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0it.md) · **Assignee:** `sase-xe.16.11.7.14.land`
**Created:** 2026-09-10 13:39:02 EDT
**Plan:** [202609/fleet\_stale\_remote\_rows.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_stale_remote_rows.md)

## Description

A machine's fleet API serves only the agents its own Agents list would present, with honest freshness and liveness, and viewers render honest statuses and authoritative counts - so a cleaned-up remote machine shows clean everywhere.

## Notes

[2026-09-10T20:44:41Z · sase-z7.land] DISCOVERED ISSUE: this epic's landed core half already changed federation normalization, but the SASE-side callers/fixtures were not adopted, so 10 fleet tests fail on clean master for any agent whose sase_core_rs is a dev build from the pinned core revision. Reproduced 2026-09-10 at SASE master HEAD 1ef9c092e with a locally built sase_core_rs from sase-core 93281c3 (workspace sase_16): tests/ace/tui/test_fleet_agents.py (7 nodes) and tests/ace/tui/test_agents_fleet_refresh_laziness.py (3 nodes) fail, e.g. test_offline_fleet_fixture_projects_rows_counts_and_diagnostics asserts len(projection.fleet_rows) == 1 and gets 0; the diagnostics payload shows the host envelope surviving with 'partial': True and 'observed_at_unix': None while every summary is dropped. Reproduces in isolation with -p no:randomly, so it is not a parallel-lane flake. Path: sase.ace.tui.models._fleet_agents_payload.host_payloads -> sase.dispatch.counts.normalize_fleet_federation_response -> Rust fleet_normalize_federation_response, changed by core commit 270e50168391 (phase sase-xe.16.11.7.14.1, 'feat(fleet): bound owner-side presentation and derive honest freshness'). It became live for local dev builds when the sase-za land agent ratcheted sase-core-revision.txt from 161206bac to 270e50168391 in SASE commit 1bfd9f0a1 for an unrelated reason (notification compaction). Published sase-core-rs 0.33.0 predates 270e501, so CI on the published wheel does not see this yet - it will the moment the floor is ratcheted. Phases sase-xe.16.11.7.14.3 (publish and adopt the new core surface) and .4 (liveness-aware rendering) are the open work this belongs to; tests/ace/tui/fleet_fixture.py needs observed_at/freshness that the new normalizer accepts, or the normalizer needs to keep unobserved summaries presentable. Found by the sase-z7 land agent while verifying epic sase-z7; sase-z7 touches no fleet or dispatch code.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.14.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.14.land/README.md) | [sase-xe.16.11.7.14](sase-xe.16.11.7.14.md) | 0 |

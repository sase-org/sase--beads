# Bead: sase-xe.16.11.7.14.5 — Athena-to-Apollo verification of the repaired view

[Bead Pages](../README.md) / [sase-xe.16.11.7.14](sase-xe.16.11.7.14.md) / sase-xe.16.11.7.14.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0it](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0it.md) · **Assignee:** `sase-xe.16.11.7.14.5` · **Size:** small
**Created:** 2026-09-10 13:39:07 EDT · **Closed:** 2026-09-10 19:40:11 EDT
**Plan:** [202609/fleet\_stale\_remote\_rows.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_stale_remote_rows.md)

## Description

live-proof: run gc reconciliation on both machines, verify athena's apollo group matches apollo's own presentation with honest counts, and prove dismissal and dead-agent transitions propagate on refresh and survive gateway restarts.

## Notes

[2026-09-10T23:39:31Z · sase-xe.16.11.7.14.5] PROPOSED FOLLOW-UP: Critical regression from owner-scope commit 270e501 (crates/sase_core/src/fleet_contract.rs) breaks fleet /hello and /summary for any host whose newly-surfaced records intent contains a control character. `intent_for_record()` (fleet_contract.rs:3805) builds the wire intent field from `raw_prompt_snippet`/`agent_meta.plan_action` and only truncates it (`trim_to_limit`) - it never strips control characters - while the summary-row validator a few hundred lines up (~line 2228, the `for (field, value) in [...("intent", ...)]` loop) calls `validate_label` which rejects ANY control character, and `char::is_control()` treats an ordinary newline in a multi-line prompt snippet as a control character. Reproduced live on apollo after this live-proof phains update+restart+gc: `curl https://apollo.tail297af1.ts.net/api/fleet/v1/hello` (and the Python `FleetGatewayClient.hello()`, and plain `sase machine status apollo`) all fail with HTTP 400 `{"code":"invalid_request","message":"intent must not contain control characters","target":"fleet_request"}`. Confirmed via `git show 270e501 -- crates/sase_core/src/fleet_contract.rs` that intent_for_record was added by this commit. Ruled out data corruption: scanned all 385 rows of apollo agent_artifact_index.sqlite (record_json) and all 624 dismissed_agents rows for control characters, found none - the bad value is synthesized live from raw_prompt_snippet at request time, not stored. Impact: this is not apollo-specific - any enrolled machine whose owner-scope-surfaced records include a normal multi-line prompt will hit this, breaking cross-machine fleet reads entirely (hello, summary, catalog all route through fleet_contract validation). This blocked live-proof verification of the apollo group view, dismiss-propagation, and restart-resilience steps - those could not be completed. Suggested fix: sanitize/strip control characters (or replace with spaces) in intent_for_record before returning, or relax validate_labels intent check to tolerate whitespace control chars (tab/newline) specifically for the intent field.

[2026-09-10T23:40:11Z · sase-xe.16.11.7.14.5] Completed the operational steps: updated apollo then athena to sase 0.17.1+393.g3e39ebdce / core 0.33.0+12.g7d6dfcfa9 and restarted both managed gateways (apollo dry-run was clean; athena update proceeded per Q1 decision despite the 5-runner warning). Ran gc reconciliation on both: apollo backfilled 56 dismissal identities (visible_rows 126->17, matching its real state of 0 running agents); athena backfilled 2716 dismissal identities and indexed 3045 previously-missing rows (visible_rows 784->1233, indexed_rows 9836->12880). BLOCKED: could not complete the cross-machine verification (athena's apollo group view, dismiss-propagation, restart-resilience) because sase machine status apollo / hello / summary now fail with HTTP 400 'intent must not contain control characters' - a regression in owner-scope commit 270e501's new intent_for_record() (crates/sase_core/src/fleet_contract.rs), which builds the wire intent field from raw_prompt_snippet without stripping control characters (e.g. newlines from ordinary multi-line prompts), then fails its own validator. Confirmed via direct curl/python reproduction and ruled out local data corruption (scanned apollo's full index, no bad stored data - the bad value is synthesized at request time). Full root cause and repro steps recorded in the PROPOSED FOLLOW-UP note on this bead. This blocks fleet hello/summary for any enrolled machine, not just apollo, and needs a core fix before this phase's acceptance gate can be verified.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.14.4](sase-xe.16.11.7.14.4.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.14.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.11.7.14.5.md) | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 0 |
| [bbugyi200.athena.toobig-55.install.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-55.install.0/README.md) | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 1 |
| [bbugyi200.athena.toobig-55.link\_health.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-55.link_health.0/README.md) | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 1 |
| [bbugyi200.athena.toobig-55.prompt\_input\_bar.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-55.prompt_input_bar.0/README.md) | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 1 |
| [bbugyi200.athena.toobig-55.test\_agent\_groups\_grouping\_mode\_tree\_status.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-55.test_agent_groups_grouping_mode_tree_status.0/README.md) | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 1 |
| [bbugyi200.athena.toobig-55.test\_agent\_runner\_slots.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-55.test_agent_runner_slots.0/README.md) | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 1 |
| [bbugyi200.athena.toobig-55.test\_fleet\_agents.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-55.test_fleet_agents.0/README.md) | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 1 |
| [bbugyi200.athena.toobig-55.test\_monitor\_gate\_capacity\_e2e.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-55.test_monitor_gate_capacity_e2e.0/README.md) | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 1 |
| [bbugyi200.athena.toobig-55.update\_handler.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-55.update_handler.0/README.md) | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9ec4dd5`](https://github.com/sase-org/sase/commit/9ec4dd5080bf50e8c9e523a04672f3660a09618c) | refactor(tui): split prompt input bar | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 2026-09-10 21:10:57 EDT |
| sase | [`05df2e0`](https://github.com/sase-org/sase/commit/05df2e0ce80aaa1ec1e08a6060f20409781a12f5) | refactor(artifact-cli): split link\_health.py into focused modules | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 2026-09-10 21:29:00 EDT |
| sase | [`3c2bd38`](https://github.com/sase-org/sase/commit/3c2bd38cb55fa7b06ffa6244ea0119371028f573) | refactor(completion): split install helpers | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 2026-09-10 21:52:38 EDT |
| sase | [`843e4b8`](https://github.com/sase-org/sase/commit/843e4b8b84424c0c2bd004ef87b2281a020c6c5d) | refactor(update): split update\_handler.py into focused modules | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 2026-09-10 22:11:49 EDT |
| sase | [`26d8425`](https://github.com/sase-org/sase/commit/26d84256ac40f4dfcfbe72a6b7ec1664dfabc26c) | test(ace): split grouping mode tree tests | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 2026-09-10 22:34:23 EDT |
| sase | [`b10a94c`](https://github.com/sase-org/sase/commit/b10a94cc203dc5adf38db9f9e2ef899f403571c5) | test(ace): split test\_agent\_runner\_slots.py into topic files | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 2026-09-10 22:53:16 EDT |
| sase | [`8b5039b`](https://github.com/sase-org/sase/commit/8b5039b571f7607b234616a9f350581564eabe50) | test: split fleet agent tests by concern | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 2026-09-10 23:14:44 EDT |
| sase | [`b43f399`](https://github.com/sase-org/sase/commit/b43f399ae34689a0dd75cc5e6bb625eef8ee4705) | test(fakey): split monitor and gate capacity e2e tests by topic | [sase-xe.16.11.7.14.5](sase-xe.16.11.7.14.5.md) | 2026-09-10 23:27:28 EDT |

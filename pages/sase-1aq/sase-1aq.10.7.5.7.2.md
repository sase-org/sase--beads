# Bead: sase-1aq.10.7.5.7.2 — Bring Apollo and Athena to the same build carrying the receipt contract

[Bead Pages](../README.md) / [sase-1aq.10.7.5.7](sase-1aq.10.7.5.7.md) / sase-1aq.10.7.5.7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aq.10.7.5.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.5.land.md) · **Assignee:** `sase-1aq.10.7.5.7.2` · **Size:** medium
**Created:** 2026-09-27 02:20:35 EDT · **Closed:** 2026-09-27 03:03:32 EDT
**Plan:** [202609/1aq\_receipts\_matched\_live\_proof.md](https://github.com/sase-org/sase--plans/blob/main/202609/1aq_receipts_matched_live_proof.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:291a07f3ea3941baac130aa6 | attached via sase artifact create --bead |
| related | file:explicit:824e26c1abb46efe06072301 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

matched_deploy: reconcile the dirty primary sase checkouts on both hosts, run the supported sase update so both hosts match origin/master for sase and sase-core, restart the gateway stack, repair the Athena agent index, and record identities.

## Notes

[2026-09-27T07:02:42Z · sase-1aq.10.7.5.7.2] matched_deploy complete 2026-09-27T~07:00Z. MATCHED BUILD: both hosts sase 0.17.1+1579.g48c3e0ddc (HEAD 48c3e0ddc, contains 700b37b384 receipt contract + receipt_cleanup) and sase-core-rs 0.34.73+50.gb57cd2131 (b57cd21); sase update -n clean on both. DIRTY RECONCILE: Apollo had 3 modified files (mobile_gateway.py, machine.py, test_machine_agent_command.py), Athena 2 (machine.py + test); every hunk verified byte-identical to origin/master (worktree files matched master exactly), full diffs backed up outside checkouts and audited as file:explicit:824e26c1abb46efe06072301 (apollo) and file:explicit:291a07f3ea3941baac130aa6 (athena), then stashed as pre-matched-deploy 20260927T064040Z (recoverable via git stash list on each host); sase-core checkouts were clean. PRE-UPDATE: no COMMITTING/LANDING agents (Apollo 1 RUNNING=self +2 WAITING; Athena 53 WAITING). Apollo update fast-forwarded sase 64fae01->48c3e0d (30 commits) + core e44af7d->b57cd21, rebuilt Rust core 5m51s; Athena update same commits, prebuild hit, 7s; both updates restarted schedulers. RESTARTS: Apollo gateway 3423950->313396 (06:51Z), scheduler ->310040 (06:50Z); Athena gateway 3084673->203449 (06:51Z), scheduler ->195015; stale Athena federation worker pid 500454 (pre-update build, 13h old despite 300s idle timeout) killed, respawns on demand. IDENTITIES/HEALTH: Apollo gateway health version 0.34.73 fleet protocol [2]; Athena gateway same; Athena sase machine list shows apollo pinned (installation_pin sase_inst_v1_8d5f...), sase machine status apollo ok (gateway 0.34.73, fleet contract schema v6); Athena sase doctor dispatch.config OK. INDEX: Apollo clean (216 visible rows). Athena had the predicted gate_shell_id repair-recommended state; verify+gc crashed (root cause below), repaired by stamp reset + gc replay: now clean (887 visible rows, 14122 indexed, dismissed identities preserved, schema v33, gate_shell_id present); sqlite backup at ~/.sase/agent_artifact_index.sqlite.pre-matched-deploy-20260927T064040Z.bak on Athena. OUT OF SCOPE LEFT AS-IS: Athena telegram_receiver proc still on pre-update code; Athena doctor project.artifact_links_aggregate ERROR (171 missing rows, pre-existing projection staleness, unrelated to deploy/dispatch).

[2026-09-27T07:02:59Z · sase-1aq.10.7.5.7.2] PROPOSED FOLLOW-UP: sase-core index open crashes instead of migrating when meta schema_version exceeds code version — Athena DB stamped 34 (no released commit has v34) made b57cd21 code skip the v31 ensure-column and fail CREATE INDEX idx_agent_artifacts_gate_shell_id in status/verify/gc/rebuild; CREATE INDEX batch should ensure columns unconditionally or open should handle version-ahead

[2026-09-27T07:03:13Z · sase-1aq.10.7.5.7.2] PROPOSED FOLLOW-UP: Athena sase doctor project.artifact_links_aggregate ERROR — aggregate missing/stale vs durable links (171 rows); pre-existing projection staleness unrelated to matched deploy, needs rebuild from durable store

[2026-09-27T07:03:32Z · sase-1aq.10.7.5.7.2] matched_deploy verified: both hosts sase 48c3e0ddc + core b57cd21, update -n clean; gateways restarted on new build (0.34.73/proto 2); Athena machine status apollo ok schema v6, dispatch.config OK; both agent indexes clean; dirty hunks proven landed, backed up as audited artifacts, stashed recoverable

## Dependencies

- **Depends on:** [sase-1aq.10.7.5.7.1](sase-1aq.10.7.5.7.1.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1aq.10.7.5.7.3](sase-1aq.10.7.5.7.3.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.7.5.7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.7.5.7.2/README.md) | [sase-1aq.10.7.5.7.2](sase-1aq.10.7.5.7.2.md) | 0 |

# Bead: sase-1ab.10.3 — Land the sase-core contract flip

[Bead Pages](../README.md) / [sase-1ab.10](sase-1ab.10.md) / sase-1ab.10.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ab.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.land.md) · **Assignee:** `sase-1ab.10.3` · **Size:** medium
**Created:** 2026-09-27 08:44:30 EDT · **Closed:** 2026-09-27 11:57:43 EDT
**Plan:** [202609/sase\_turn\_rename\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename_finish.md)

## Description

core-flip: re-apply the orphaned contract-flip diff onto current sase-core master, give the gate_turn_id column migration artifact-index schema 35, prove current sase master against it, and land the feat! commit on sase-core origin/master.

## Notes

[2026-09-27T14:21:23Z · sase-1ab.10.3] Mirror constants pin-bump (sase-1ab.10.4) must move after the flip lands: src/sase/core/agent_scan_wire_records.py AGENT_SCAN_WIRE_SCHEMA_VERSION 10->11 and AGENT_ARTIFACT_INDEX_SCHEMA_VERSION 34->35 (extend SUPPORTED_* frozensets to include 11 and 35); src/sase/procs/models/common.py PROC_WIRE_SCHEMA_VERSION 3->4 (SUPPORTED set already includes 4); src/sase/dispatch/models.py FLEET_PROTOCOL_VERSION 2->3; src/sase/core/agent_launch_wire_records.py LAUNCH_PLAN_WIRE_SCHEMA_VERSION 2->3. No Python mirrors exist for RUNNER_CAPACITY_POLICY (6->7), AGENT_HOLD_WIRE (2->3), PROC_DISPATCH_WIRE (1->2), or FLEET_CONTRACT_SCHEMA (6->7); those are core-internal with dynamic probes. Flip commit not yet landed; sase-against-new-core proof still pending (extension build exceeded turn budget, handed to monitor).

[2026-09-27T14:22:20Z · sase-1ab.10.3] PROPOSED FOLLOW-UP: sase-core finalizer run_view prose still says shell-concept wording (wire.rs:36,105,120 doc comments: "Which kind of shell produced a run", "every member shell run", "one concrete shell finalizer run"; precedence.rs:192 "the shell sealed a plan"). No serialized shell-named fields there; classification/reword belongs to the acceptance sweep, not the contract flip.

[2026-09-27T14:22:34Z · sase-1ab.10.3] PROPOSED FOLLOW-UP: gateway test fleet_launch_replays_delayed_launch_and_reconciles_visible_row failed once under full sase-core check with Timeout("snapshot_refresh") then passed alone and on full re-run; matches known flake bead sase-15g, not the flip. No action.

[2026-09-27T15:16:30Z · sase-1ab.10.3--1] PROPOSED FOLLOW-UP: sase-against-new-core triage (monitor nh6xmnwdtnvv, tool run 883d8e1b3109f0ed6483a64dc4c52ebd): 11 flip-caused failures fixed dual-core-compatibly in sase (index-35 reader, fleet-protocol 2/3 handshake, contract 6/7 pin, turn-spelling normalization tolerance) — see close note. Remaining 16 failures + 54 symvision are base-identical (sase tree was clean): finish.md KNOWN covers config-schema receipt key (1ah), kind-coverage receipt slots (1ah), header overflow (1b8), import budget (13p), grok wording (1as), timezone guard (1b2), history-wire 33-pins (1b2), symvision backlog (1ay); not on that list but equally base-identical: completion snapshot drift x2, turn-terminology shell mentions, prompts-overlay trash count, deck FINAL catalog/spread/card, marker-path audit. Suggest routing those to the acceptance sweep or their owning beads.

[2026-09-27T15:53:58Z · sase-1ab.10.3--2] PROPOSED FOLLOW-UP: d07 just-check triage flags tests/ace/tui/widgets/test_agent_header_panel.py::test_expanded_overflowing_header_claims_half_page_scroll as NEW (no owner), but it is KNOWN: finish.md routes this exact node to sase-1b8, and it fails identically on the clean base tree (verified via git stash + single-test rerun this turn: deck_scroll.scroll_y 2.0 vs 0.0 with zero sase changes applied). Not flip-caused; leave for sase-1b8/acceptance sweep.

[2026-09-27T15:57:43Z · sase-1ab.10.3--2] Core flip landed via accepted final declaration (sase-core feat!: shell->turn, origin/master was 2fb5c57; flip commits on top. sase: dual-core-compat fixes). Verified: sase-core sase tool run check GREEN (run d37e90668c98db167855137ce1c5ffb8); sase just check (tool run 8d22afae1bf67c400c1182c86ce37be7): 9918 passed, remaining failures all KNOWN/base-identical per finish.md (1b2 timezone+history pins, 1ah-class, 1b8 header, 1ay symvision, terminology) incl. header proven base-identical via stash rerun this turn; the one self-inflicted machine_service handshake failure fixed (test now expects [2,3]) and rerun green (9 passed). sase-core-revision.txt untouched (sase-1ab.10.4 owns the pin bump).

## Dependencies

- **Depends on:** [sase-1ab.10.1](sase-1ab.10.1.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1ab.10.2](sase-1ab.10.2.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1ab.10.4](sase-1ab.10.4.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.10.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.10.3.md) | [sase-1ab.10.3](sase-1ab.10.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`650c313`](https://github.com/sase-org/sase/commit/650c313b715880b2ffb0d7337d0a92b39381c21f) | feat(contracts): negotiate flipped sase-core contracts dual-core-compatibly | [sase-1ab.10.3](sase-1ab.10.3.md) | 2026-09-27 11:59:46 EDT |
| sase-core | [`sase-core@75e27f9`](https://github.com/sase-org/sase-core/commit/75e27f9a8576a1b5ddba04fbd6ad594afef9b96b) | feat!: rename shell contracts to turn across core wires | [sase-1ab.10.3](sase-1ab.10.3.md) | 2026-09-27 12:05:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ab.10.3--2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.10.3.md

<!-- sase:referenced-by:end -->

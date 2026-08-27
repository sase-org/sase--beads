# Bead: sase-ud.13.1.5 — One nested family\_shell wire record at schema v7

[Bead Pages](../README.md) / [sase-ud.13.1](sase-ud.13.1.md) / sase-ud.13.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.md) · **Assignee:** `sase-ud.13.1.5` · **Size:** medium
**Created:** 2026-08-27 08:49:08 EDT · **Closed:** 2026-08-27 11:05:31 EDT
**Plan:** [202608/gate\_shell\_status\_collapse.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shell_status_collapse.md)

## Description

wire-v7: fold the flat `monitor_*` and `gate_*` field blocks on `AgentMetaWire` and `DoneMarkerWire` into one nested `family_shell` record in both the Rust core and the Python wire, bump the agent-scan wire schema to 7, and keep every existing reader working through a compatibility projection.

## Notes

[2026-08-27T15:04:59Z · sase-ud.13.1.5] PROPOSED FOLLOW-UP: lint (feature flags) fails on master right now with 'rule 7: closed flag bead sase-ul still has a surviving link_pager definition' — unrelated to this phase (I never touched feature_flags/registry.py); looks like bead sase-ul's link_pager retirement landed as a bead close without the matching code removal reaching this tree yet. Verify whether that removal is in flight elsewhere or needs re-opening.

[2026-08-27T15:05:31Z · sase-ud.13.1.5] Folded the flat monitor_*/gate_* field blocks on AgentMetaWire and DoneMarkerWire into one nested FamilyShellWire record (kind discriminator + shared fields + FamilyShellMonitorWire/FamilyShellGateWire sub-blocks) in both the Rust core (crates/sase_core/src/agent_scan/wire.rs, scanner.rs's new family_shell_from_object compat-shim for on-disk marker JSON, agent_runtime.rs's is_real_monitor_member_record/is_real_gate_member_record/is_runner_slot_occupying_record) and the Python wire (new src/sase/core/agent_scan_wire_family_shell.py with family_shell_from_mapping() as the one shared flat-JSON/nested-dict compat projection). Bumped AGENT_SCAN_WIRE_SCHEMA_VERSION to 7 on both sides plus tools/validate_sase_core_rs's hardcoded probe literal. Updated every real consumer discovered via two broad Explore-agent sweeps (Python and Rust) beyond the three the plan named: gate_shell/models.py, monitor/models.py, _meta_enrichment_wire.py, running_listing.py, _done_loaders.py, runner_slots/_admission.py, catalog_agents.py, wait_watch/_classify.py, wait_dependency_resolution/_artifact_state.py (which needed family_shell_from_mapping specifically because WaitDependencyIndex.build() feeds it flat on-disk dicts while _wait_live_rows.py feeds it asdict()-nested ones), gate_shell/store.py, monitor/store.py, and _agent_list_entry_builder.py/_wait_live_rows.py per the plan. Rewrote ~20 test files/38+ call sites off flat monitor_*/gate_* kwargs onto the nested shape, including tests/monitor/_fixtures.py's generic _load() helper which was the actual root cause of an initial 68-test regression (it bypassed the Rust scanner and read flat on-disk JSON via known_field_kwargs without the family_shell projection). Verified: cargo fmt/clippy -D warnings/test clean across the full sase-core workspace (sase_core: ~2000 tests; sase_core_py PyO3 bindings: 101 tests) and just check's full lint stage plus just test-scoped (13296 passed, 7 skipped, 0 failed) clean here. sase bead epic-symbols sase-ud.13.1.5 reported no --epic-symbol entries to resolve. The one just check failure I saw (lint (feature flags): closed bead sase-ul's link_pager definition still present) is unrelated to this phase and is recorded as a PROPOSED FOLLOW-UP note.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ud.13.1.5/README.md) | [sase-ud.13.1.5](sase-ud.13.1.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`588a1cf`](https://github.com/sase-org/sase/commit/588a1cfaeb86331ce59ec5e649a77682674f2015) | feat(agent-scan): fold monitor\_\*/gate\_\* wire fields into nested family\_shell at schema v7 | [sase-ud.13.1.5](sase-ud.13.1.5.md) | 2026-08-27 11:06:51 EDT |
| sase-core | [`sase-core@f0224ef`](https://github.com/sase-org/sase-core/commit/f0224efa66a0f31f1d4b96b7e4bcd04f2902c80b) | feat(agent-scan): fold monitor\_\*/gate\_\* wire fields into nested family\_shell at schema v7 | [sase-ud.13.1.5](sase-ud.13.1.5.md) | 2026-08-27 11:07:52 EDT |

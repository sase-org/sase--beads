# Bead: sase-x7.5 — Prepare canonical shared formats and coordinated wire contracts

[Bead Pages](../README.md) / [sase-x7](README.md) / sase-x7.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gk.md) · **Assignee:** `sase-x7.5` · **Size:** large
**Created:** 2026-09-05 18:55:30 EDT
**Plan:** [202609/canonical\_only\_fleet\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_only_fleet_cutover.md)

## Description

shared-format-bridge: Plan and implement parser-aware conversions for Patch, plan, gate, prompt, and catalog records, plus the necessary Rust/PyO3/host/plugin contract changes. Stage a tested bridge release and temporary sunset flags only where a real mixed-format interval exists.

## Notes

[2026-09-10T09:58:01Z · sase-x7.5] Planning handoff: authored a child EPIC plan (sase_plan_shared_format_bridge.md), not a tale. Tier rationale for the land agent to audit: (1) the canonical Patch wire, catalog discriminator and conversion contracts all live in sase-core, and the host cannot call a new binding until a core release is published, the sase-core-rs floor is raised (today >=0.32.61,<0.33.0) and sase-core-revision.txt is ratcheted -- CI job release-core-floor-smoke runs tools/check_sase_core_rs_bindings against the declared floor, so this is the real second landing the parent epic forbids collapsing; (2) census gaps G5 (LSP/gateway/PyO3 wire inventory) and G2 (four-plugin legacy-symbol audit) are assigned to this phase and must decide each formats disposition BEFORE any converter is written; (3) a coherent cohort means host + sase-core (incl. PyO3) + up to four plugin suites plus isolated 3.12/3.14 wheel smoke, which outruns one turn. Seven medium phases: bridge-inventory, bridge-core-contracts, residual-format-proofs, host-wire-adoption, patch-record-converter, gate-bundle-converter, bridge-cohort. All Rust core work is concentrated in one phase so no two agents edit shared core exports/parsers/bindings concurrently. Scope was tightened against measurement, not widened: only Patch project-spec records and gate v2 request envelopes get converters, because those are the only families with live legacy records on athena; plan prefixes, plan-chain suffixes, chat-link timestamps and memory note types get proof receipts instead. No production data is converted and nothing is deployed -- sase-x7.8 owns that.

[2026-09-10T09:58:34Z · sase-x7.5] REPORTED FOR PLAN REVIEW (not decided by this phase): the Rust IssueWire fields changespec_name and changespec_bug_id appear in 9,807 / 9,803 of the 29,930 append-only bead events (only 11 events carry a non-empty value) and are also keys in the issues.jsonl projection and the gateway mobile bead summary wire. Renaming them on the wire would force the historical replay path to accept the old keys, which broadens the epic named historical exception -- the parent plan requires reporting that concrete conflict before widening it. The child plan phase bridge-inventory records the evidence and a recommendation (keep the stored event key names, confine any canonical rename to regenerated outward surfaces); no phase of the child epic renames those two fields. Also closing census finding F6: the gate schema discriminator IS reproducible on current master at src/sase/notification_gates/model_validation.py:11-12 (LEGACY_GATE_REQUEST_SCHEMA_VERSION=2, GATE_REQUEST_SCHEMA_VERSION=3), with live readers at notification_gates/hashing.py:36,139 and debug_rendering.py:163; model_request.py already refuses anything but v3 on the creation path, so v2 is read-only compatibility over settled records.

## Dependencies

- **Depends on:** [sase-x7.2](sase-x7.2.md) ✓ · ⧖ 2026-09-05
- **Depends on:** [sase-x7.4](sase-x7.4.md) ✓ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.8](sase-x7.8.md) ◐ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.5.md) | [sase-x7.5](sase-x7.5.md) | 0 |

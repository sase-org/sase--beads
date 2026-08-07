# Bead: sase-gn.1 — One tab per notification, counted in the core

[Bead Pages](../README.md) / [sase-gn](README.md) / sase-gn.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uh/README.md) · **Assignee:** `sase-gn.1` · **Size:** medium
**Created:** 2026-08-06 19:27:20 EDT · **Closed:** 2026-08-06 20:10:25 EDT
**Plan:** [202608/bead\_snooze\_and\_notification\_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_snooze_and_notification_indicator.md)

## Description

notif-tab-model: make tab ownership a single-valued core rule that splits Snoozed from Muted, publish ordered per-tab counts on the notification snapshot, and reduce the Python tag helpers to a thin adapter.

## Notes

[2026-08-07T00:09:37Z · sase-gn.1] PROPOSED FOLLOW-UP: publish a sase-core release carrying classify_notification_tabs and bump pyproject sase-core-rs window — dev installs build the binding from the local checkout, but published installs pinned to sase-core-rs>=0.18.4,<0.19.0 lack the new binding and would raise from require_rust_binding("classify_notification_tabs"). Land the crate release and window bump before this phase ships as a published wheel.

[2026-08-07T00:09:49Z · sase-gn.1] PROPOSED FOLLOW-UP: flaky test under the parallel lane — tests/ace/tui/modals/test_artifact_files_modal_copy.py::test_artifact_file_modal_copy_anchors_pdf_markdown_source_path failed once in `just check` and passes in isolation and on rerun; unrelated to notification tabs.

[2026-08-07T00:10:06Z · sase-gn.1] PROPOSED FOLLOW-UP: sase/memory/sase_beads.md and docs may later need the Snoozed notification tab documented alongside the bead snooze status (D7 forbids memory edits in this epic); the land agent should route that to the owner.

[2026-08-07T00:10:25Z · sase-gn.1] Tab ownership is now single-valued in the Rust core. Added crates/sase_core/src/notifications/tabs.rs with the D1 precedence (__snoozed__ > __muted__ > declared panel > hitl > errors > first stored tag > general), NotificationTabWire/NotificationTabClassificationWire, snapshot.tabs, and a classify_notification_tabs pyo3 binding; counts_for now delegates to the same single tabs_and_counts_for pass so per-tab counts and the legacy counters cannot disagree. Python side: _NotificationTabWire + tabs on the snapshot wire (known_field_kwargs tolerant), classify_notification_tabs on the facade, and notification_modal_tags reduced to a thin adapter (classify_notification_modal_tabs returns ordered tabs plus a row-id -> tab-key dict; NotificationModal caches it so per-row membership is a dict lookup, one FFI call per rebuild). RESERVED_GATE_PANELS extended to errors/general/hitl/muted/snoozed. Verified: 11 new crate tests + full cargo test --workspace (1246 lib tests) green, cargo fmt/clippy clean; new tests/test_notification_modal_tags.py (two-tag regression, snoozed-vs-muted split, snoozed gate leaving its panel tab, adapter-vs-snapshot parity, tab counts partitioning the legacy counters) plus updated modal/gate tests; just check fully green (all lint gates + 26.5k scoped tests). docs/notifications.md documents the precedence. Crate and Python changes are left uncommitted for the epic's land agent; a PROPOSED FOLLOW-UP records the sase-core release + pyproject window bump the published wheel needs.

[2026-08-07T00:11:05Z · sase-gn.1] Rust core tab classification + Python adapter; cargo test --workspace and just check green

## Dependencies

- **Blocks:** [sase-gn.2](sase-gn.2.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.1/README.md) | [sase-gn.1](sase-gn.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7ee5105`](https://github.com/sase-org/sase-core/commit/7ee51051f61b79b679d9f591cbca5b79c7cc433b) | feat(notifications): make tab ownership a single-valued core rule | [sase-gn.1](sase-gn.1.md) | 2026-08-06 20:11:36 EDT |
| sase | [`5e6a94a`](https://github.com/sase-org/sase/commit/5e6a94a3890d192dca6091d2165783381c8348e3) | feat(ace-tui): give each notification exactly one tab, counted in the core | [sase-gn.1](sase-gn.1.md) | 2026-08-06 20:14:05 EDT |

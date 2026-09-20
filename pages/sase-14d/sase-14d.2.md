# Bead: sase-14d.2 — Config surface and Python facade

[Bead Pages](../README.md) / [sase-14d](README.md) / sase-14d.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0o7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0o7.md) · **Assignee:** `sase-14d.2` · **Size:** medium
**Created:** 2026-09-20 13:11:31 EDT · **Closed:** 2026-09-20 14:39:08 EDT
**Plan:** [202609/notification\_delivery\_rules.md](https://github.com/sase-org/sase--plans/blob/main/202609/notification_delivery_rules.md)

## Description

config-rules: ratchet the pinned core revision, add ace.notification_rules to default_config.yml and the JSON schema, and add the token-cached Python facade that reads the rules and resolves deliveries through the new binding.

## Notes

[2026-09-20T18:37:58Z · sase-14d.2] PROPOSED FOLLOW-UP: raise the sase-core-rs package floor before release - pyproject still declares >=0.34.48 but src/sase/core/notification_store_facade.py now calls resolve_notification_deliveries, which first ships in v0.34.70 (on PyPI); tools/ratchet_core_window --report-only already proposes the pyproject.toml + uv.lock bump, and the release-core-floor-smoke gate will flag the missing binding at the old floor until it lands (same cadence the agent_hold_deadlock_reaches pin used: source pin first, floor via the window ratchet).

[2026-09-20T18:38:24Z · sase-14d.2] PROPOSED FOLLOW-UP: master is red independent of this epic - just _lint-symvision fails at clean HEAD 9316a24e5b on 26 unused public symbols from other in-flight work (sdd/_store_clone_admission.py, sdd/_store_clone_remote.py, ace/tui/models/_agent_runner_slot_capacity.py, completion/runtime_cache_generation.py coherent, service/host_support.py, service/host_reporting.py), so just check stops at the symvision stage; and 7 tests fail deterministically at clean HEAD (tests/test_capacity_gate_to_admission.py x2, tests/ace/tui/test_epic_panel_arrival_frames.py x4, tests/ace/tui/test_lazy_tier2_reconcile_apply.py::test_changed_query_incomplete_load_after_reconcile_rearms). Verified by stashing this phase and re-running both.

[2026-09-20T18:39:08Z · sase-14d.2] Implemented (commit is host-finalized). Pinned sase-core-revision.txt to 92625404deb4f25880d08d20a6efc3c03e16e03d (v0.34.70 release, descendant of a7f26b2 'feat(notifications): add delivery rule matcher and resolve_notification_deliveries binding'); just install rebuilt the venv and the real binding resolves rules. Added ace.notification_rules: [] + comment block to default_config.yml and an array-of-objects schema (additionalProperties:false at rule and match level, six criteria as string|array-of-string, priority -1000..1000, sound string) to sase.schema.json. Added src/sase/notifications/delivery.py (NotificationSound/NotificationDelivery, DEFAULT_NOTIFICATION_DELIVERY, SOUND_BELL/NONE/FILE, notification_delivery_rules(), resolve_notification_deliveries(notifications)); wire types NotificationSoundWire/NotificationDeliveryWire + notification_deliveries_from_list in core/notification_store_wire.py; facade resolve_notification_deliveries(rules, notifications) beside classify_notification_tabs (require_rust_binding call site is statically visible, so REQUIRED_BINDINGS is unchanged). Contract for downstream phases: notification_delivery_rules() returns a token-cached tuple of wire-shaped rule dicts (do not mutate); a malformed rule (non-dict, unknown rule/match key, wrong-typed field, null match, null/non-string criterion, priority outside schema bounds) is dropped WHOLE rather than partially applied, so a rule never matches more broadly than written, and an unnamed rule's rule[<index>] label counts the surviving list; resolve_notification_deliveries returns one NotificationDelivery per input row in order with toast, sound (kind bell|none|file, path), toast_rule, sound_rule, and short-circuits to DEFAULT_NOTIFICATION_DELIVERY with no FFI/config work for an empty batch or no rules (parity with the core default is tested); it does a config read plus an FFI hop, so call it on the worker thread. Verified: 43 new tests in tests/test_notification_delivery.py pass against the real core (config parsing incl. malformed/bare-string/missing match, default-empty, token-cache invalidation, core-default parity, end-to-end quiet-task-beads + mbp-chime resolution, wire schema/unknown-kind/count-mismatch guards); just fmt/fix clean; just check: ruff, mypy, feature flags, pyscripts, test waits, changelog, terminology, keep-sorted all pass; symvision passes for every symbol this phase added (epic-symbol entries re-keyed to sase-14d.4 for NotificationDelivery/NotificationSound and sase-14d.5 for notification_delivery_rules; sase bead epic-symbols sase-14d.2 reports none) but the gate is red at clean HEAD on 26 unrelated symbols from other in-flight work; just test-scoped escalated to the full suite: 43992 passed, 7 failed, all 7 reproduced on clean HEAD via stash (unrelated capacity-gate/epic-panel/lazy-tier2 tests). Two PROPOSED FOLLOW-UP notes recorded (raise sase-core-rs floor to 0.34.70 via ratchet_core_window; pre-existing symvision/test breakage at HEAD).

## Dependencies

- **Depends on:** [sase-14d.1](sase-14d.1.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14d.4](sase-14d.4.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14d.5](sase-14d.5.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14d.6](sase-14d.6.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14d.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.2/README.md) | [sase-14d.2](sase-14d.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9a99238`](https://github.com/sase-org/sase/commit/9a99238cdf0e9e415575f5b11559cdb2f29c59c2) | feat(notifications): add ace.notification\_rules config and Python delivery facade | [sase-14d.2](sase-14d.2.md) | 2026-09-20 14:40:33 EDT |

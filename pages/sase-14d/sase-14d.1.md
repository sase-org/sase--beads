# Bead: sase-14d.1 — Rule matcher in the Rust core

[Bead Pages](../README.md) / [sase-14d](README.md) / sase-14d.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0o7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0o7.md) · **Assignee:** `sase-14d.1` · **Size:** medium
**Created:** 2026-09-20 13:11:30 EDT · **Closed:** 2026-09-20 13:29:13 EDT
**Plan:** [202609/notification\_delivery\_rules.md](https://github.com/sase-org/sase--plans/blob/main/202609/notification_delivery_rules.md)

## Description

core-rules: add notification delivery rule wire types, the first-match-per-field resolver, a case-insensitive glob matcher, and the batched resolve_notification_deliveries PyO3 binding to sase-core, reusing tab_key_for for the tab criterion.

## Notes

[2026-09-20T17:28:37Z · sase-14d.1] PROPOSED FOLLOW-UP: observability doctor check needs its own "unparseable glob" test - the core glob matcher is deliberately total (an unclosed `[` is a literal `[`, like fnmatch), so no pattern errors at match time; flag unclosed `[` (and blank sound, empty criterion list = matches nothing, reversed range) from Python or via a small core helper rather than expecting a parse error.

[2026-09-20T17:29:13Z · sase-14d.1] Implemented in sase-core (linked repo; commit is host-finalized by the finalizer, so the SHA does not exist yet - config-rules should take the sase-core commit whose subject is 'feat(notifications): add delivery rule matcher and resolve_notification_deliveries binding'). Added crates/sase_core/src/notifications/rules.rs (NotificationRuleWire/RuleMatchWire/SoundWire/DeliveryWire, case-insensitive glob matcher in-crate, first-match-per-field resolver, resolve_notification_delivery + resolve_notification_deliveries), exported from notifications/mod.rs, and the PyO3 binding resolve_notification_deliveries(rules: list[dict], notifications: list[dict]) -> list[dict] in sase_core_py (allow_threads, registered, documented in the module binding list). Contract for downstream phases: unknown keys at rule or match level raise ValueError naming rules[<idx>]; criteria take a bare string or list; sound is {kind: bell|none|file, path}; deliveries carry schema_version, toast, sound, and toast_rule/sound_rule (rule name, else zero-based rule[<index>] in the list passed in, omitted when the built-in default applied); blank sound and rules setting neither field are inert; empty criterion list matches nothing. Verified: just check in sase-core exit 0 (fmt, clippy -D warnings, full workspace tests) with 44 new rules.rs tests (glob edge cases: empty pattern, bare *, unclosed [, [*], non-ASCII; no-rules default for all 9 survey row shapes; first-match-per-field with both *_rule names; priority reorder; tab:beads suppresses TaskTriage not axe ViewErrorReport; gates/GATES/hitl equivalence; all-of/any-of; serde unknown-key rejection) plus 2 binding tests. No epic-symbol entries for this phase.

## Dependencies

- **Blocks:** [sase-14d.2](sase-14d.2.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14d.4](sase-14d.4.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14d.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.1/README.md) | [sase-14d.1](sase-14d.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@a7f26b2`](https://github.com/sase-org/sase-core/commit/a7f26b2b2018901501c443931c518c86d5469110) | feat(notifications): add delivery rule matcher and resolve\_notification\_deliveries binding | [sase-14d.1](sase-14d.1.md) | 2026-09-20 13:31:24 EDT |

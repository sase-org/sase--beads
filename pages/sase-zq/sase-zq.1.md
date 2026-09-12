# Bead: sase-zq.1 — Shared bead decision contract

[Bead Pages](../README.md) / [sase-zq](README.md) / sase-zq.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0jp](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0jp.md) · **Assignee:** `sase-zq.1` · **Size:** medium
**Created:** 2026-09-11 15:33:36 EDT · **Closed:** 2026-09-11 16:45:23 EDT
**Plan:** [202609/explicit\_bead\_action.md](https://github.com/sase-org/sase--plans/blob/main/202609/explicit_bead_action.md)

## Description

core_contract: add a strict Rust bead-action policy and Python bindings, plus authenticated finalizer context for the assigned bead.

## Notes

[2026-09-11T20:44:05Z · sase-zq.1] Exported API for integrate_policy (sase-zq.2):

sase-core bead_action contract (schema_version=1), unused until Python callers switch:
- parse_bead_action_field(payload) -> Optional[close|keep]; omitted key is None; rejects boolean/null/empty/unknown and any do_not_close_bead key with migration text "use -B keep or -B close"
- decide_bead_action / decide_bead_action_from_json: host facts assigned_bead_id, commit_method (create_commit|create_pull_request|create_proposal), repository_scope (primary|linked|external|sdd|unknown), primary_repository_identified, bead_action, bead_status (in_progress|closed|other|unreadable|unchecked)
- dispositions: keep, close (close_bead=true), close_idempotent, unassociated
- keep never requires status lookup; close requires identified primary + create_commit/create_pull_request + in_progress or closed; failed primary lookup does not grant close; proposal close is rejected
- validate_finalizer_bead_decision(context, decision) and validate_finalizer_assigned_bead_binding(context, expected)

FinalizerContextWire additive assigned_bead {bead_id, primary_repo_obligation_id?}; FINALIZER_WIRE_SCHEMA_VERSION stays 2; omitted association serializes identically and keeps the unassociated digest.

PyO3: bead_action_wire_schema_version, parse_bead_action_field, decide_bead_action, validate_finalizer_bead_decision, validate_finalizer_assigned_bead_binding.

Do not bump sase-core-rs>=0.34.0,<0.35.0 until release-plz publishes this API. No Python fallback.

Verified: sase-core fmt-check + clippy; cargo test --workspace (with LD_LIBRARY_PATH workaround for sase-xv) including bead_action policy table and PyO3 JSON/digest/assignment-mismatch tests; sase mypy+pytest on the additive FinalizerAssignedBeadWire converters.

[2026-09-11T20:44:40Z · sase-zq.1] PROPOSED FOLLOW-UP: just check mypy fails in src/sase/llm_provider/continuation_budget.py:176 — _int_setting assigns config.get(key) (object) onto raw inferred as str | None from env.get; unrelated to bead-action, observed on a tree whose only sase edits are FinalizerAssignedBeadWire converters.

[2026-09-11T20:45:23Z · sase-zq.1] Added unused sase-core bead_action policy (schema 1) and additive FinalizerContextWire.assigned_bead (wire schema stays 2). Verified: core fmt-check+clippy; cargo test --workspace including UX-table policy tests and PyO3 JSON/digest/assignment-mismatch bindings (LD_LIBRARY_PATH workaround for sase-xv); sase mypy+pytest on FinalizerAssignedBeadWire converters. No CLI/workflow call sites switched yet.

## Dependencies

- **Blocks:** [sase-zq.2](sase-zq.2.md) ✓ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zq.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zq.1/README.md) | [sase-zq.1](sase-zq.1.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3102a21`](https://github.com/sase-org/sase-core/commit/3102a210930db10c5ff44a584526090599b77c29) | feat: Shared bead decision contract (sase-zq.1) | [sase-zq.1](sase-zq.1.md) | 2026-09-12 05:19:34 EDT |
| sase | [`ed11c13`](https://github.com/sase-org/sase/commit/ed11c135483179910fcf5f2c89a3431facfd570d) | feat: Shared bead decision contract (sase-zq.1) | [sase-zq.1](sase-zq.1.md) | 2026-09-12 05:19:53 EDT |

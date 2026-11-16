# Bead: sase-1t2.8.1.6 — Enable finalizer latching and expose the CLI contract

[Bead Pages](../README.md) / [sase-1t2.8.1](sase-1t2.8.1.md) / sase-1t2.8.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t2.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.8.md) · **Assignee:** `sase-1t2.8.1.6` · **Size:** medium
**Created:** 2026-11-16 04:09:08 EST · **Closed:** 2026-11-16 12:26:00 EST
**Plan:** [202611/hijack\_latch\_boundaries.md](https://github.com/sase-org/sase--plans/blob/main/202611/hijack_latch_boundaries.md)

## Description

activate_cli: return latched decisions only for supported finalizing or staged agent turns, route the orchestrator to request_latch, add mutually exclusive cancel/explain/now flags and exit 3, and document the delivered behavior.

## Notes

[2026-11-16T17:00:19Z · sase-1t2.8.1.6--1] PROPOSED FOLLOW-UP: just check lint (symvision) reports reset_lower_macros_cache and reset_project_identity_caches as unused public (KNOWN, witness 0db2857e7b11b260268acce89ddca65e3); subjects live in src/sase/config/local_trust_*.py untouched by this phase, reproduce on clean base

[2026-11-16T17:24:51Z · sase-1t2.8.1.6--1] PROPOSED FOLLOW-UP: tests/fakey/test_agent_hijack_e2e.py::test_hijack_reload_escalate_inherits_both_repos_through_finalizer fails with AttributeError is_agent_session_container_row on SimpleNamespace in src/sase/ace/tui/models/_agent_status_apply.py:115, and tests/gate_turn/test_creator_origin_retention.py fails at cleanup_stale_running_entries()==0; both fail identically on clean base with this phase stashed, so neither is owned by activate_cli

[2026-11-16T17:26:00Z · sase-1t2.8.1.6--1] activate_cli verified: docs-contract gate clean after trimming agent-statuses.md HIJACK PENDING row + footer (check_docs errors 1->0); regenerated cli_spec.json via just sync-completion-spec and bumped mutex-group count 22->23 for the new hijack cancel/explain/now group; focused suites green (102 passed: activate_cli/facts/latch/reconcile/ledger/lock-order/core/custody/preview + completion build/snapshot) and sase-core agent_hijack 87 passed. Remaining just-check reds reproduce identically on clean base and are recorded as PROPOSED FOLLOW-UP: 2 KNOWN symvision unused-publics (witness 0db2857), fakey hijack e2e AttributeError in TUI overlay, gate_turn stale-cleanup assertion.

## Dependencies

- **Depends on:** [sase-1t2.8.1.5](sase-1t2.8.1.5.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.8.1.7](sase-1t2.8.1.7.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.8.1.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.8.1.6.md) | [sase-1t2.8.1.6](sase-1t2.8.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c58ecb8`](https://github.com/sase-org/sase-core/commit/c58ecb80996dfcb6d0066e72ee0e8b2d843d16ec) | feat(agent-hijack): latch finalizer turns with staged-adoption boundary wire | [sase-1t2.8.1.6](sase-1t2.8.1.6.md) | 2026-11-16 12:28:16 EST |

# Bead: sase-y3.3 — Machine writes move to hidden host-owned sidecar clones

[Bead Pages](../README.md) / [sase-y3](README.md) / sase-y3.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04n.md) · **Assignee:** `sase-y3.3` · **Size:** large
**Created:** 2026-09-07 15:14:47 EDT · **Closed:** 2026-09-07 19:51:03 EDT
**Plan:** [202609/machine\_link\_mutations\_off\_primary.md](https://github.com/sase-org/sase--plans/blob/main/202609/machine_link_mutations_off_primary.md)

## Description

hidden-clone-machine-writes: add a machine-context artifact-link store resolution rooted at hidden host-owned sidecar clones following the agents-sidecar precedent, bless those clones for machine mutation in the ownership contract without weakening primary-#0 refusal, switch the artifact_link_backfill chop and agents-sync referenced-by drain to it, and verify primary clones converge via pull-based auto-sync.

## Notes

[2026-09-07T23:51:03Z · 06m--1] Implemented and verified. Added src/sase/sdd/_artifact_link_machine_store.py (resolve_machine_artifact_link_store, re-exported from artifact_link_store.py) resolving machine-context artifact-link writes to hidden host-owned sidecar clones; extended the ownership contract with AccessKind.HOST_OWNED_SIDECAR + HOST_OWNED_SIDECAR_WORKSPACE_NUM and _hidden_sidecar_machine_context wired into _infer_machine_context, without weakening primary-#0 refusal; switched the two background anchors (sase_chop_artifact_link_backfill.py, agents_sync/referenced_by_publication.py) onto the machine store.

VERIFIED LANES:
1. Focused suites, 30 passed: tests/sdd/test_artifact_link_machine_store.py, tests/workspace_provider/test_ownership_hidden_sidecar.py, tests/agents_sync/test_referenced_by_publication.py, tests/sdd/test_artifact_link_hidden_clone_e2e.py, tests/test_axe_chop_artifact_link_backfill.py.
2. just check: every lint gate green; its scoped lane escalated to the full suite (context-baseline-stale).
3. just check-full via monitor wtg57wkt2vza (26m02s): every lint gate, SASE validation, and committed-plan gate green; 39411 passed, 14 skipped, 5 failed. All 5 failures are unrelated to this phase and pre-existing on master -- tests/test_xprompt_directive_contract.py::test_runtime_directive_vocabulary_matches_core_contract plus 4 nodes in tests/test_xprompt_directive_completion_parity.py. Nothing in the artifact-link stores, ownership contract, artifact_link_backfill chop, agents-sync referenced-by drain, or sidecar auto-sync failed.

UNRELATED FAILURE DISPOSITION: root-caused rather than filed as a flake. sase-xe.15 (ac1ba1be9) removed the remote_dispatch flag on the Python side, but sase-core HEAD 9dc37f4 / v0.32.40 still has "dispatch" => Some("remote_dispatch") at crates/sase_core/src/editor/wire.rs:598, so the core contract and Rust LSP still gate %dispatch while the Python side does not. Deterministic in isolation, so not a flake and not fixable by just install. /sase_new_task routed this to the still-in-progress epic sase-xe that owns the flag removal: recorded there as a DISCOVERED ISSUE note with the reproduction and proposed fix, plus a root-cause note on sase-y9 whose flake diagnosis it supersedes.

The earlier two ref:plan keymap parametrized failures (tests/test_keymaps_patch_grouping_binding.py) did not recur in check-full, so no flake bead was filed for them. sase bead epic-symbols sase-y3.3 reports no entries.

## Dependencies

- **Depends on:** [sase-y3.1](sase-y3.1.md) ✓ · ⧖ 2026-09-07
- **Depends on:** [sase-y3.2](sase-y3.2.md) ✓ · ⧖ 2026-09-07
- **Blocks:** [sase-y3.4](sase-y3.4.md) ✓ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y3.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-y3.3.md) | [sase-y3.3](sase-y3.3.md) | 0 |

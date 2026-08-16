# Bead: sase-mq.5 — Background bead mutations off canonical primary clones

[Bead Pages](../README.md) / [sase-mq](README.md) / sase-mq.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.035](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.035.md) · **Assignee:** `sase-mq.5` · **Size:** medium
**Created:** 2026-08-15 23:40:21 EDT · **Closed:** 2026-08-16 03:06:50 EDT
**Plan:** [202608/primary\_workspace\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/primary_workspace_ownership.md)

## Description

background-mutators: route runner and scheduled bead writers through writable workspace-local stores while retaining canonical stores for reads.

## Notes

[2026-08-16T07:05:19Z · sase-mq.5] PROPOSED FOLLOW-UP: escalated just check full suite is red on pre-existing TUI/ops/gate failures — 84 failed + 45 errors: live run.launch sidecar pollutes gate.act/ops (sase-mq.1), PatchFilterBar #patch-filter-input missing, fork footer expects lowercase f vs F, QueryEditModal timeouts, plus test_artifact_directory_operation_sites_are_reviewed extra site reset_replay._clear_owned_paths. None are background bead writers.

[2026-08-16T07:06:23Z · sase-mq.5] PROPOSED FOLLOW-UP: bead_claim_checks still takes two operational leases per project per tick (refreshed read snapshot, then write batch) — fuse read+reconcile under one lease so periodic work does not churn claims.

[2026-08-16T07:06:50Z · sase-mq.5] Background bead writers (waiting claims, bead_claim_checks, external issue mirror) now mutate leased workspace-local stores instead of canonical_beads_dir_for_project. Runners reuse a claimed workspace only when beads are a separate workspace-local sidecar; otherwise a short operational lease is acquired. After publication they mark a beads sidecar sync hint instead of pulling the primary clone. CLI sync-external stays user-directed. Verified: new background_store tests cover sidecar reuse, in-tree/local/separate_repo lease, concurrent claim+mirror, and primary HEAD/status/refs unchanged until auto-sync; existing claims/claim_checks/mirror tests passed. just lint green. just check lint+validate green; scoped run escalated (core-identity-changed, justfile) to 30794 passed / 84 failed / 45 errors — pre-existing TUI/ops/gate plus artifact-audit _clear_owned_paths (noted).

[2026-08-16T07:08:03Z · sase-mq.5] Background bead writers (waiting claims, bead_claim_checks, external issue mirror) mutate leased workspace-local stores instead of canonical_beads_dir_for_project. Runners reuse a claimed workspace only when beads are a separate workspace-local sidecar. After publication they mark a beads sidecar sync hint. CLI sync-external stays user-directed. Verified: background_store tests cover sidecar reuse, in-tree/local/separate_repo lease, concurrent claim+mirror, and primary HEAD/status/refs unchanged until auto-sync; existing claims/claim_checks/mirror tests passed. just lint green. just check lint+validate green; scoped run escalated (core-identity-changed, justfile) to 30794 passed / 84 failed / 45 errors — pre-existing TUI/ops/gate plus artifact-audit _clear_owned_paths.

## Dependencies

- **Depends on:** [sase-mq.3](sase-mq.3.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mq.7](sase-mq.7.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mq.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mq.5/README.md) | [sase-mq.5](sase-mq.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4b30309`](https://github.com/sase-org/sase/commit/4b30309e0f639e44063102544f621419c5cdbb9a) | feat(bead): lease workspace-local stores for background writers | [sase-mq.5](sase-mq.5.md) | 2026-08-16 03:08:53 EDT |

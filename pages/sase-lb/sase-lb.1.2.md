# Bead: sase-lb.1.2 — Authoritative workspace-directory to workspace-number lookup

[Bead Pages](../README.md) / [sase-lb.1](sase-lb.1.md) / sase-lb.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.015](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.015.md) · **Assignee:** `sase-lb.1.2` · **Size:** small
**Created:** 2026-08-14 11:09:31 EDT · **Closed:** 2026-08-14 11:45:10 EDT
**Plan:** [202608/workspace\_claim\_invariant.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_claim_invariant.md)

## Description

lookup: add a registry-backed helper that resolves a checkout directory to its owning workspace number.

## Notes

[2026-08-14T15:45:10Z · sase-lb.1.2] Added resolve_workspace_num_for_dir() in src/sase/workspace_provider/lookup.py, resolving a checkout directory to its owning workspace number via the registry (falling back to WorkspaceStore.resolve for the primary), normalizing ~/symlinks/trailing-slashes before comparing, never guessing from the basename. Exported from the workspace_provider package. Added tests/workspace_provider/test_workspace_lookup.py covering primary->0, managed checkout->its number, trailing-slash/symlink/~-relative equivalence, out-of-project->None, and unregistered-but-existing dir->None. Verified with just install (rebuilt sase_core_rs) and just check (all lint gates + scoped tests passed, exit 0).

## Dependencies

- **Blocks:** [sase-lb.1.3](sase-lb.1.3.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-lb.1.5](sase-lb.1.5.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lb.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lb.1.2/README.md) | [sase-lb.1.2](sase-lb.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8a0fd07`](https://github.com/sase-org/sase/commit/8a0fd07a062b87ecce619d4779a8707631d5cf81) | feat(workspace\_provider): add directory-to-workspace-number lookup helper | [sase-lb.1.2](sase-lb.1.2.md) | 2026-08-14 11:46:39 EDT |

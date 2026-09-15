# Bead: sase-116.2 — Route reads and writes through one explicit operation context

[Bead Pages](../README.md) / [sase-116](README.md) / sase-116.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0l4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0l4.md) · **Assignee:** `sase-116.2` · **Size:** medium
**Created:** 2026-09-15 09:03:32 EDT · **Closed:** 2026-09-15 11:54:56 EDT
**Plan:** [202609/global\_bead\_id\_resolution.md](https://github.com/sase-org/sase--plans/blob/main/202609/global_bead_id_resolution.md)

## Description

operation-context: provide routed read and mutation contexts, preserve store ownership and publication guarantees, and integrate the Rust fast dispatch with the shared target resolver.

## Notes

[2026-09-15T15:54:19Z · sase-116.2] Phase API: use BeadOperationContext plus resolve_operation_context_for_targets/local_operation_context from sase.bead.operation_context; cli_common accepts bead_context on project/read/mutation helpers; fast-path bead commands route target operands to one owner store and preserve invocation cwd.

[2026-09-15T15:54:56Z · sase-116.2] Verified: focused operation-context and fast-path tests passed; just check passed including symvision, with only the existing non-fatal core-floor stale warning.

## Dependencies

- **Depends on:** [sase-116.1](sase-116.1.md) ✓ · ⧖ 2026-09-15
- **Blocks:** [sase-116.3](sase-116.3.md) ◐ · ⧖ 2026-09-15
- **Blocks:** [sase-116.4](sase-116.4.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-116.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-116.2/README.md) | [sase-116.2](sase-116.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dbe3cd4`](https://github.com/sase-org/sase/commit/dbe3cd4bcea0991d1a561be9465594173ef27c04) | feat(bead): route operations through explicit contexts | [sase-116.2](sase-116.2.md) | 2026-09-15 11:57:33 EDT |

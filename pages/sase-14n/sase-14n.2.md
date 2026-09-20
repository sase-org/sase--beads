# Bead: sase-14n.2 — Restore the complete-history latch reset on a changed query key

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oe.md) · **Assignee:** `sase-14n.2` · **Size:** medium
**Created:** 2026-09-20 17:14:09 EDT · **Closed:** 2026-09-20 17:27:45 EDT
**Plan:** [202609/fix\_triaged\_bug\_and\_ci\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_triaged_bug_and_ci_beads.md)

## Description

latch: decide whether the keep-the-larger-cache change or the test expectation is wrong for an incomplete tier1 load under a changed history query key, then fix that side.

## Notes

[2026-09-20T21:27:45Z · sase-14n.2] Latch phase done: the keep-the-larger-cache change was wrong, test expectation was right — restored the latch-key gate in _loading_apply.py so a changed-query incomplete tier1 load disarms the complete-history latch. Verified: reconcile file 11/11, boundary file 20/20, view-picker file included (42 passed total), ruff clean. just check still aborts at the symvision gate, which fails identically on a clean tree and belongs to sibling phase sase-14n.1.

## Dependencies

- **Blocks:** [sase-14n.7](sase-14n.7.md) ◐ · ⧖ 2026-09-20
- **Blocks:** [sase-14n.8](sase-14n.8.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.2/README.md) | [sase-14n.2](sase-14n.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`54fff48`](https://github.com/sase-org/sase/commit/54fff48206f82a4328c41edd4859a2aa65d95b75) | fix(tui): restore complete-history latch reset on a changed query key | [sase-14n.2](sase-14n.2.md) | 2026-09-20 17:29:32 EDT |

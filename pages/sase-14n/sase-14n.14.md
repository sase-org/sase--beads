# Bead: sase-14n.14 — Surface why workspace preparation failed

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.14

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oe.md) · **Assignee:** `sase-14n.14` · **Size:** medium
**Created:** 2026-09-20 17:14:23 EDT · **Closed:** 2026-09-20 19:55:33 EDT
**Plan:** [202609/fix\_triaged\_bug\_and\_ci\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_triaged_bug_and_ci_beads.md)

## Description

workspace_error: carry the underlying git or update failure out of prepare_workspace into the raised error and the run log instead of discarding it.

## Notes

[2026-09-20T23:55:33Z · sase-14n.14--2] sase tool run check green (monitor ksmtmx5ms3wy exit 0); same evidence as sase-14m plus 6 stale bool-contract tests updated to raise/None contract: agents-lock x3, workspace open x1, bead rescue x2

## Dependencies

- **Depends on:** [sase-14n.1](sase-14n.1.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.14](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-14n.14.md) | [sase-14n.14](sase-14n.14.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`090f3ad`](https://github.com/sase-org/sase/commit/090f3add5a36095f441d4319fbe024d7f83d49cd) | fix(axe): surface underlying workspace preparation failure reason | [sase-14n.14](sase-14n.14.md) | 2026-09-20 19:57:35 EDT |

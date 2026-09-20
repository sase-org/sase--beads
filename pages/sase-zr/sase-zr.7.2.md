# Bead: sase-zr.7.2 — Receipt-derived approval labels and honest commit status

[Bead Pages](../README.md) / [sase-zr.7](sase-zr.7.md) / sase-zr.7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.07](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.07.md) · **Assignee:** `sase-zr.7.2` · **Size:** medium
**Created:** 2026-09-16 14:25:11 EDT · **Closed:** 2026-09-19 11:44:53 EDT
**Plan:** [202609/sase\_zr\_close\_out.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_zr_close_out.md)

## Description

approval-projection: derive TALE/EPIC APPROVED from the acceptance receipt on every load path, show PLAN COMMITTED only after archive success and roll it back on failure, surface the failed outcome as a distinct status, and publish response.json, shell terminal state and the refresh pulse before post-terminal epic launch preparation.

## Notes

[2026-09-19T15:44:53Z · sase-zr.7.2--1] Receipt-derived TALE/EPIC APPROVED from acceptance on every load path; PLAN COMMITTED only after archive success and rolled back to PLAN/EPIC FAILED on archive/execution failure; response.json, shell terminal state, and refresh pulse publish before post-terminal epic launch. just check: 43393 passed, 23 skipped; only flake tests/pager/test_rendered_link_failures.py::test_copy_of_a_missing_path_keeps_the_logical_token (failed under full-suite contention, passed in isolation twice). Targeted approval-projection/settlement/enrichment tests 103 passed.

## Dependencies

- **Depends on:** [sase-zr.7.1](sase-zr.7.1.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-zr.7.3](sase-zr.7.3.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.7.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-zr.7.2.md) | [sase-zr.7.2](sase-zr.7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bfc6142`](https://github.com/sase-org/sase/commit/bfc6142fcffb9500eb4a91a8f875be52946bda87) | feat(gates): project receipt-derived approval labels and honest commit status | [sase-zr.7.2](sase-zr.7.2.md) | 2026-09-19 12:54:23 EDT |

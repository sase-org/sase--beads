# Bead: sase-80.1 — Live axe state path resolution

[Bead Pages](../README.md) / [sase-80](README.md) / sase-80.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-80.1`
**Created:** 2026-07-20 01:56:54 UTC
**Plan:** [202607/axe\_test\_isolation\_leak.md](https://github.com/sase-org/sase--plans/blob/main/202607/axe_test_isolation_leak.md)

## Description

'Live axe state path resolution' section: replace import-time axe state-dir constants with live path functions so the autouse test-home isolation actually covers axe lifecycle state, and migrate all src and test call sites.

## Notes

COMMIT: 4bcabb31e

## Dependencies

- **Blocks:** [sase-80.2](sase-80.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-80.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-80.1/README.md) | [sase-80.1](sase-80.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`cc99b7a`](https://github.com/sase-org/sase/commit/cc99b7a3bbb13ab7273abe1d44e3aed9d6852bf3) | fix(axe): resolve state paths at call time (sase-80.1) | [sase-80.1](sase-80.1.md) | 2026-07-20 12:06:19 |

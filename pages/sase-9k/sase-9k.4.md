# Bead: sase-9k.4 — Edit wait priority from the ACE wait modal

[Bead Pages](../README.md) / [sase-9k](README.md) / sase-9k.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9k.4` · **Size:** medium
**Created:** 2026-07-25 14:38:34 UTC
**Plan:** [sase/repos/plans/202607/wait\_priority.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/wait_priority.md)

## Description

'Edit wait priority from the ACE wait modal' section: add a priority field to the ACE wait modal and its directive/marker persistence path, and make sure editing other wait fields never clobbers an existing wait_priority.

## Notes

Implemented ACE wait-priority editing: modal validation/prefill/clear semantics, %wait(priority=N) round-trip, explicit marker/meta persistence, no-clobber behavior for omitted priority edits, run-now clearing, Agent loader explicit-state propagation, and updated modal PNG golden. Verification: 105 focused functional tests passed; wait-modal visual snapshot passed; all just check non-test gates passed. Full suite reached 21,983 passes; remaining failures were unrelated pre-existing/flaky daemon mock-count, suite-gate capacity, diff-cache, and tools-panel visual tests.

## Dependencies

- **Depends on:** [sase-9k.2](sase-9k.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9k.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9k.4/README.md) | [sase-9k.4](sase-9k.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3a8540f`](https://github.com/sase-org/sase/commit/3a8540f321764da347f69c38eced0b96c1f0119f) | feat(ace): edit wait priority from wait modal (sase-9k.4) | [sase-9k.4](sase-9k.4.md) | 2026-07-25 16:21:34 |

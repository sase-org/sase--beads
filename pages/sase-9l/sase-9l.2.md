# Bead: sase-9l.2 — Deny-by-default bead-store write guard

[Bead Pages](../README.md) / [sase-9l](README.md) / sase-9l.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9l.2` · **Size:** medium
**Created:** 2026-07-25 14:56:30 UTC
**Plan:** [202607/bead\_store\_pytest\_isolation.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_store_pytest_isolation.md)

## Description

'Deny-by-default bead-store write guard' section: extend the existing pytest state-write guard with a bead-store rule, wire it into every bead write chokepoint including the Rust CLI fast path, and repair every remaining test the armed guard refuses.

## Notes

Implemented assert_bead_store_write_sandboxed with deny-by-default pytest semantics and explicit override coverage. Guarded all bead mutation facade chokepoints before Rust binding lookup and guarded Rust CLI fast-path verbs create/open/update/close/dep/rm while leaving reads unguarded. No production code or fixture uses SASE_ALLOW_UNSANDBOXED_BEAD_WRITES; its only set is the primitive override unit test. Repaired the axe daemon spawn test to stub command construction so unrelated Git probes are not counted as daemon Popen calls. Validation: focused guard/facade/fast-path/daemon suite 36 passed; full non-slow sweep 21947 passed, 7 skipped with one unrelated daemon test failure subsequently repaired and passing; slow lane 7 passed, 2 skipped. The production plans sidecar stayed clean; intervening HEAD/digest changes audited as legitimate concurrent bead/SDD commits with no pytest-fixture create commit. Formatting, ruff, mypy, pyscripts, Symvision, toobig, committed-plan validation passed. Full just check is currently prevented at SASE validation by five externally managed sase_agents_status provider skill files awaiting regeneration in the chezmoi repo.

## Dependencies

- **Depends on:** [sase-9l.1](sase-9l.1.md) ✓
- **Blocks:** [sase-9l.3](sase-9l.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9l.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9l.2/README.md) | [sase-9l.2](sase-9l.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`289222b`](https://github.com/sase-org/sase/commit/289222b19ca37c8fdf34a86112aa3997807abf96) | fix(tests): deny unsandboxed pytest bead-store writes (sase-9l.2) | [sase-9l.2](sase-9l.2.md) | 2026-07-25 17:12:33 |

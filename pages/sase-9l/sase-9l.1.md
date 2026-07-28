# Bead: sase-9l.1 — Pytest sandbox containment for bead-store resolution

[Bead Pages](../README.md) / [sase-9l](README.md) / sase-9l.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9l.1` · **Size:** medium
**Created:** 2026-07-25 14:56:27 UTC
**Plan:** [202607/bead\_store\_pytest\_isolation.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_store_pytest_isolation.md)

## Description

'Pytest sandbox containment' section: publish the pytest sandbox root, stop checkout-marker and primary-workspace discovery from escaping it inside pytest, and repair the shared bead test fixtures that currently resolve to the real sidecar store.

## Notes

Published SASE_PYTEST_SANDBOX_DIR per pytest worker; bounded checkout-marker, primary-workspace, and CLI workspace-context discovery; converted leaking fixtures to marker-backed in-sandbox resolution. Verification: 736 focused tests passed; plans-sidecar issues.jsonl SHA-256 and HEAD remained unchanged. just check passed formatting and all lint gates through mypy/symvision/toobig, then stopped on pre-existing generated sase_beads skill drift in the external chezmoi repo; committed-plan validation separately passed 3162 files with zero errors or warnings.

## Dependencies

- **Blocks:** [sase-9l.2](sase-9l.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9l.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9l.1/README.md) | [sase-9l.1](sase-9l.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`5ae5e9a`](https://github.com/sase-org/sase/commit/5ae5e9a4dcdc51c496009259baa4e0625ba44b9c) | fix(tests): contain bead resolution in pytest sandbox (sase-9l.1) | [sase-9l.1](sase-9l.1.md) | 2026-07-25 15:19:11 |

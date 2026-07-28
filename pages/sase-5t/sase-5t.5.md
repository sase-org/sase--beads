# Bead: sase-5t.5 — Phase 5 — Migrate sase to the published package

[Bead Pages](../README.md) / [sase-5t](README.md) / sase-5t.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5t.5`
**Created:** 2026-07-12 21:44:54 UTC · **Closed:** 2026-07-14 10:36:11 UTC
**Plan:** [202607/symvision\_extraction\_1.md](https://github.com/sase-org/sase--plans/blob/main/202607/symvision_extraction_1.md)

## Description

Work in the sase repo/workspace and run just install first. Replace the vendored pyvision integration with symvision>=0.1.0,<0.2.0, rename pragmas and live references, update tests/config/docs, and verify just symvision plus just check. Memory files, AGENTS.md, and provider shims require explicit user permission in this phase agent's own conversation; otherwise leave them untouched and flag the follow-up.

## Notes

Registry verification and the consumer migration were previously performed from ephemeral workspace state, so the earlier closure did not prove a landed SASE change. Recovery baseline on 2026-07-13 confirms the consumer migration is durably reachable from origin/master as commit 039204fe2.

Recovery implementation completed in the current workspace with user-authorized protected-memory edits: memory/pyvision.md was replaced by memory/symvision.md; root and tools agent instructions, generated memory index, and provider shims were refreshed through sase memory init --no-commit; the public symvision recipe now delegates to _lint-symvision; regression coverage prevents restoration of _lint-pyvision or tools/pyvision-*.

Verification: just install resolved symvision==0.1.0 from the registry; just symvision passed; focused Justfile/CI tests passed (14 passed); sase memory init --check passed and provider shims match their AGENTS.md sources; the live-surface audit has no pyvision references outside intentional negative regression assertions; just test passed (16,787 passed, 7 skipped). just check passed Python/Markdown formatting and all lint stages (keep-sorted, ruff, mypy, pyscripts, symvision, toobig), then stopped at SASE validation only because the pre-existing plans companion needs generated SDD README/map refresh; memory init and sdd validate themselves are current/passing, and no recovery change touches SDD state.

Keep Phase 5 and epic sase-5t open until these uncommitted recovery edits have a durable SASE commit and ChangeSpec/PR reachable from origin/master.

## Dependencies

- **Depends on:** [sase-5t.4](sase-5t.4.md) ✓
- **Blocks:** [sase-5t.6](sase-5t.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.7e](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.7e/README.md) | [sase-5t.5](sase-5t.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`039204f`](https://github.com/sase-org/sase/commit/039204fe2e8d62d685f1e7d089ba077989ed128a) | feat: Migrate from pyvision to symvision (sase-5t.5) | [sase-5t.5](sase-5t.5.md) | 2026-07-13 10:50:19 |
| [`3d5fe9c`](https://github.com/sase-org/sase/commit/3d5fe9c50a8e3d68f04bf1a5a033247e65f79c0a) | fix: complete Symvision migration recovery (sase-5t.5) | [sase-5t.5](sase-5t.5.md) | 2026-07-13 11:04:43 |

# Bead: sase-1q.2 — Phase 2: Vendor and Clean SASE Pragmas

[Bead Pages](../README.md) / [sase-1q](README.md) / sase-1q.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-1q.2`
**Created:** 2026-05-01 06:13:30 UTC · **Closed:** 2026-05-01 06:40:49 UTC
**Plan:** [202605/pyvision\_alias\_pragmas.md](https://github.com/sase-org/sase--plans/blob/main/202605/pyvision_alias_pragmas.md)

## Description

After Phase 1 is committed and applied, re-vendor pyvision into this repo, update references such as Justfile, remove all # pyvision: tests/... pragmas from src/sase while keeping legitimate non-test pragmas, update tools/AGENTS.md policy, and run the required pyvision/check commands.

## Notes

COMMIT: 17b86264

## Dependencies

- **Depends on:** [sase-1q.1](sase-1q.1.md) ✓
- **Blocks:** [sase-1q.3](sase-1q.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`ba8d90b`](https://github.com/sase-org/sase/commit/ba8d90bc58ef4e01ed7428c7051e9364e233c305) | fix: vendor pyvision test reference scanning (sase-1q.2) | [sase-1q.2](sase-1q.2.md) | 2026-05-01 06:38:24 |
| [`17b8626`](https://github.com/sase-org/sase/commit/17b86264182400b16bde1a51b688f93e687d7722) | fix: apply pyvision pragma cleanup (sase-1q.2) | [sase-1q.2](sase-1q.2.md) | 2026-05-01 06:40:55 |

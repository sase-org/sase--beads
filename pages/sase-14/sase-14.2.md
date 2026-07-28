# Bead: sase-14.2 — Phase 0B: Public API Routing

[Bead Pages](../README.md) / [sase-14](README.md) / sase-14.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-14.2`
**Created:** 2026-04-29 03:52:41 UTC · **Closed:** 2026-04-29 04:30:06 UTC
**Plan:** [202604/rust\_backend\_phase0.md](https://github.com/sase-org/sase--plans/blob/main/202604/rust_backend_phase0.md)

## Description

Route existing public parser, query, graph index, status transition, and selected status field helper APIs through the sase.core facade while preserving Python implementations with _python names.

## Notes

COMMIT: 3daf294f

## Dependencies

- **Depends on:** [sase-14.1](sase-14.1.md) ✓
- **Blocks:** [sase-14.4](sase-14.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`4f6fd31`](https://github.com/sase-org/sase/commit/4f6fd312e0f9c26e39610915ba2cc214a3ad0d07) | feat(core): route public ChangeSpec/query/status APIs through sase.core facade (sase-14.2) | [sase-14.2](sase-14.2.md) | 2026-04-29 04:30:10 |

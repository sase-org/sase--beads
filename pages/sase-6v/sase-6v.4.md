# Bead: sase-6v.4 — Chop SDK and builtin script consolidation

[Bead Pages](../README.md) / [sase-6v](README.md) / sase-6v.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6v.4`
**Created:** 2026-07-18 19:41:59 UTC
**Plan:** [202607/chops\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202607/chops_redesign.md)

## Description

'Chop SDK and builtin script consolidation' section: ship a small chop-author SDK, collapse the cloned builtin chop scripts onto it via a registry, migrate builtins to structured results, and retire the cl_submitted_checks legacy alias.

## Notes

Added public sase.chops SDK and builtin registry/runtime; migrated all 12 builtin chop modules to structured results while preserving summaries; removed the cl_submitted_checks console alias; added SDK, registry, output-contract, and audit coverage. Verified with focused tests and full just check.

## Dependencies

- **Depends on:** [sase-6v.3](sase-6v.3.md) ✓
- **Blocks:** [sase-6v.5](sase-6v.5.md) ✓

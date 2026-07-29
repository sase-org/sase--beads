# Bead: sase-ar.2 — ChopReport builder in the sase.chops SDK

[Bead Pages](../README.md) / [sase-ar](README.md) / sase-ar.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ar.2` · **Size:** medium
**Created:** 2026-07-29 13:50:00 UTC · **Closed:** 2026-07-29 14:29:42 UTC
**Plan:** [202607/axe\_chop\_reports.md](https://github.com/sase-org/sase--plans/blob/main/202607/axe_chop_reports.md)

## Description

sdk: add a typed `ChopReport` builder plus `ChopResultBuilder.report` to the public `sase.chops` SDK so chop packages compose reports without hand-writing JSON or markup, and document the contract in docs/axe.md.

## Notes

[2026-07-29T14:29:42Z · sase-ar.2] Implemented the public ChopReport/Tone SDK, ChopResultBuilder.report integration, normalization and defensive validation, exports, docs, and report coverage. Verified 13 focused SDK tests and the full suite (23,511 passed, 7 skipped); Ruff, mypy, pyscripts, Symvision, toobig, and formatting passed. just check reached SASE validation, which remains blocked only by unrelated generated-skill drift and the existing axe_chop_reports plan prompt-link error.

## Dependencies

- **Depends on:** [sase-ar.1](sase-ar.1.md) ✓
- **Blocks:** [sase-ar.5](sase-ar.5.md) ✓

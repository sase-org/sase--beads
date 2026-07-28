# Bead: sase-5t.1 — Phase 1 — Create the repo and port the tool (code + dev tooling)

[Bead Pages](../README.md) / [sase-5t](README.md) / sase-5t.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5t.1`
**Created:** 2026-07-12 21:43:54 UTC
**Plan:** [202607/symvision\_extraction\_1.md](https://github.com/sase-org/sase--plans/blob/main/202607/symvision_extraction_1.md)

## Description

Work in ~/projects/github/bbugyi200/symvision/ (create it in this phase as the sibling checkout specified by the plan). Create the public repository, scaffold packaging and development tooling, port pyvision to symvision, add smoke tests, and verify checks plus behavior parity.

## Notes

Created public github.com/bbugyi200/symvision with master as default; ported pyvision into focused typed modules with symvision naming, hatchling/uv tooling, self-dogfooding, toobig checks, and four CLI smoke tests. just check passes. Real SASE scratch-tree parity run produced identical normalized diagnostics and matching exit status. Pushed feat commit 34bf0fa.

## Dependencies

- **Blocks:** [sase-5t.2](sase-5t.2.md) ✓

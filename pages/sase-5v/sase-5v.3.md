# Bead: sase-5v.3 — Full test suite + coverage gate

[Bead Pages](../README.md) / [sase-5v](README.md) / sase-5v.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5v.3`
**Created:** 2026-07-12 23:21:10 UTC
**Plan:** [202607/basher\_extraction.md](https://github.com/sase-org/sase--plans/blob/main/202607/basher_extraction.md)

## Description

Work directly in ~/projects/github/bbugyi200/basher/; port the bashunit semantics, add focused unit and integration coverage, enforce the honest coverage gate, and leave just check green.

## Notes

Ported all pyvendor and bugyi.sh bashunit semantics to pytest; added focused config, provenance, engine, CLI/status JSON, dry-run, update, export, project discovery, and rendering coverage; standard pytest/just check now enforces 95% coverage. Verified just check: 56 passed, 95.86% coverage, lint/mypy/symvision/toobig/shellcheck green.

## Dependencies

- **Depends on:** [sase-5v.2](sase-5v.2.md) ✓
- **Blocks:** [sase-5v.4](sase-5v.4.md) ✓

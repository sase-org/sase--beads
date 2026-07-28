# Bead: sase-5n.2 — Phase 2: Harden pyvision In Chezmoi

[Bead Pages](../README.md) / [sase-5n](README.md) / sase-5n.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5n.2`
**Created:** 2026-07-09 02:16:15 UTC · **Closed:** 2026-07-09 02:40:31 UTC
**Plan:** [202607/pyvision\_markdown\_pragmas.md](https://github.com/sase-org/sase--plans/blob/main/202607/pyvision_markdown_pragmas.md)

## Description

Update the source pyvision script so markdown paths can no longer satisfy pragma validation.

## Notes

Updated chezmoi pyvision source to reject local .md/.markdown pragma targets before local file validation; switched existing local pragma tests to .toml config coverage; added .md and .markdown rejection tests. Validation: bashunit ./tests/bash/pyvision_test.sh passed (24 tests).

## Dependencies

- **Depends on:** [sase-5n.1](sase-5n.1.md) ✓
- **Blocks:** [sase-5n.3](sase-5n.3.md) ✓

# Bead: sase-6v.7 — Builtin refresh-docs chop and xprompt workflow retirement

[Bead Pages](../README.md) / [sase-6v](README.md) / sase-6v.7

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6v.7`
**Created:** 2026-07-18 19:42:27 UTC
**Plan:** [202607/chops\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202607/chops_redesign.md)

## Description

'Builtin refresh-docs chop and xprompt workflow retirement' section: replace the refresh_docs xprompt workflow with a builtin proposal-emitting chop script driven by the commits-since trigger and target fan-out, delete the four chop-owned workflows from sase/xprompts/, migrate tests off those fixtures, and update all chops documentation.

## Notes

Added the SDK-based sase_chop_refresh_docs console script with update/polish proposals, wait_on chaining, prompt overrides, and fail-closed validation. Retired the four chop-owned xprompt workflows, migrated loader/notification fixtures to synthetic names, removed obsolete workflow-specific tests, and updated axe/config/xprompt/plugin/current architecture docs plus the public schema. Verification: focused suites pass; strict docs build passes; formatting, Ruff, mypy, pyscript, Symvision, and size lint pass; full suite reached 18829 passed with only 44 unrelated Agents-tab PNG renderer-drift failures. Aggregate validation is also blocked by five stale globally deployed sase_run skill copies outside this repo.

## Dependencies

- **Depends on:** [sase-6v.6](sase-6v.6.md) ✓
- **Blocks:** [sase-6v.8](sase-6v.8.md) ✓

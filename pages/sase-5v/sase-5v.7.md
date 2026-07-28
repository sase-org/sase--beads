# Bead: sase-5v.7 — Migrate chezmoi and retire the scripts

[Bead Pages](../README.md) / [sase-5v](README.md) / sase-5v.7

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5v.7`
**Created:** 2026-07-12 23:22:15 UTC · **Closed:** 2026-07-13 10:56:41 UTC
**Plan:** [202607/basher\_extraction.md](https://github.com/sase-org/sase--plans/blob/main/202607/basher_extraction.md)

## Description

Work in the chezmoi repo opened via sase workspace open -p chezmoi -r "<reason>" <workspace_num>; keep ~/lib/bugyi.sh continuously available, replace its management with basher export, retire pyvendor and old tests, run chezmoi verification, apply the committed change, and smoke-test real consumers.

## Notes

COMMIT: 835e8f19

## Dependencies

- **Depends on:** [sase-5v.6](sase-5v.6.md) ✓

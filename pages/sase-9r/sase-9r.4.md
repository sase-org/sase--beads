# Bead: sase-9r.4 — Machine-managed SDD git ignores the user's rerere config

[Bead Pages](../README.md) / [sase-9r](README.md) / sase-9r.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9r.4` · **Size:** small
**Created:** 2026-07-26 10:48:43 UTC
**Plan:** [202607/sdd\_clone\_integration\_race.md](https://github.com/sase-org/sase--plans/blob/main/202607/sdd_clone_integration_race.md)

## Description

'Machine-managed SDD git ignores the user's rerere config' section: disable rerere for every SASE-issued git command in a machine-managed SDD store and purge the resolution cache that the user's global `rerere.autoupdate` already leaked into the shared plans clone.

## Notes

Implemented SDD git rerere hardening for machine-managed stores:
- run_sdd_git now invokes git with -c rerere.enabled=false and -c rerere.autoupdate=false.
- bead conflict resolver direct git calls use the same SDD git argv builder, including git add during semantic conflict repair.
- Added regressions proving ambient rerere config is overridden and machine-managed integration does not leave rr-cache files behind.
- Updated existing tests that assumed unprefixed git argv or a moving current date.

Operational cleanup:
- Opened the shared production plans clone through sase repo open.
- Purged its leaked .git/rr-cache (207 entries / 421 files).
- Scanned existing machine-managed SDD sidecar clones from the SASE repo inventory and purged remaining rr-cache files from the current sase project plans clones; a rescan reported no remaining rr-cache files.

Verification:
- just install passed.
- Focused rerere/conflict tests passed.
- just check passed fmt, ruff, mypy, symvision, toobig, SASE validation, and committed-plans validation. Full pytest still has unrelated suite-level failures: test_suite_gate_integration and diff_cache passed in isolation; the reproducible remaining issue is a tiny pre-existing ACE PNG mismatch in test_renamed_generic_family_root_png_snapshot (429/1,520,532 pixels). No parent epic closed.

## Dependencies

- **Blocks:** [sase-9r.8](sase-9r.8.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`b8ec882`](https://github.com/sase-org/sase/commit/b8ec882ce10a20b445845667fd923792b7e19f94) | fix(sdd): ignore rerere for managed git commands (sase-9r.4) | [sase-9r.4](sase-9r.4.md) | 2026-07-26 11:30:53 |
